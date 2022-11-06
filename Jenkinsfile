pipeline {

    agent any


    stages {
        stage ('Git') {
            steps {
               echo "Getting Project from Git"; 
               git branch: 'master',
               url : 'https://github.com/oussamahosni/RepoTpAchat';
           }
        }
       
        stage("Build") {
            steps {
                sh "mvn -version"
                sh "mvn clean"
                sh 'mvn compile'
            }
        }

	stage("Sonar") {
            steps {
                sh "mvn sonar:sonar -Dsonar.login=admin -Dsonar.password=root"
            }
        }
        
        stage("SRC Analysis Testing") {
            steps {
                sh "mvn sonar:sonar"
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
