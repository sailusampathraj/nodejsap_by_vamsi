pipeline{
    agent any
    environment {
        NODE_PATH = "/"
        NODE_LOG_LEVEL = "fatal"
    }
    stages {
        stage('CleanWorkspace') {
            steps {
                cleanWs()
            }
        } 
   
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
