pipeline{
    agent any
   
    stages {
        stage('CleanWorkspace') {
            steps {
                cleanWs()
            }
        } 
   
        stage('Build') {    
           steps {
             nodejs(nodeJSInstallationName: 'nodejs17.5.0'){
                    sh 'npm install'
                   // sh 'npm run start'
                  withSonarQubeEnv('sonar-scanner') {
                   sh 'npm install sonar-scanner'
                   sh 'npm run sonar' 
                } 
             } 
           }
       }
        
    }
}
