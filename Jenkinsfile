pipeline {

    agent any


    stages {
        stage ('GIT') {
            steps {
               echo "Getting Project from Git"; 
                git branch: "master", 
                    url: "https://github.com/oussamahosni/RepoTpAchat.git";
            }
        }
       
        stage("Build") {
            steps {
                sh "mvn -version"
                bat "mvn clean package -DskipTests"
            }
        }

      
    }
   
    post {
        always {
            cleanWs()
        }
    }
    
}
