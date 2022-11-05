pipeline {

    agent any


    stages {
        stage ('Git') {
            steps {
               echo "Getting Project from Git"; 
              git(url: 'https://github.com/oussamahosni/RepoTpAchat', branch: 'master', credentialsId: 'tpachat')
           }
        }
       
        stage("Build") {
            steps {
                sh "mvn -version"
                bat "mvn clean package -DskipTests"
            }
        }

	stage("Sonar") {
            steps {
                bat "mvn sonar:sonar"
            }
        }
        
        stage("SRC Analysis Testing") {
            steps {
                bat "mvn sonar:sonar"
            }
        }
        
        stage("Build Docker image") {
            steps {
                sh "..............."
            }
        }

        stage("Deploy Artifact to private registry") {
            steps {
                sh "..............."
            }
        }

        stage("Deploy Dokcer Image to private registry") {
            steps {
                sh "..............."
            }
        }
      
    }
   
    post {
        always {
            cleanWs()
        }
    }
    
}
