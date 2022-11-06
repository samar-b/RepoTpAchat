pipeline {

    agent any


    stages {
        stage ('Git') {
            steps {
               echo "Getting Project from Git"; 
               git branch: 'master',
	       credentialsId: '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'
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
                sh "docker build -t oussamahosni/projetdevops-backend . "
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
