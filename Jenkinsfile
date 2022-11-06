pipeline {

    agent any


    stages {
        stage ('Git') {
            steps {
               echo "Getting Project from Git"; 
               git(url: 'https://github.com/oussamahosni/RepoTpAchat', branch: 'master', credentialsId: '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')
           }
        }
       
        stage("Build") {
            steps {
                sh "mvn -version"
                sh "mvn clean"
                sh 'mvn compile'
            }
        }

	stage("Sonar Analysis Testing") {
            steps {
                sh "mvn sonar:sonar -Dsonar.login=admin -Dsonar.password=root"
            }
        }
        
        
        stage("Build Docker image") {
            steps {
                sh "docker build -t oussamahosni/projetdevops-backend . "
            }
        }

        stage("Deploy Artifact to private registry") {
            steps {
                sh "docker login -u oussamahosni -p docker123"
		
            }
        }

        stage("Deploy Dokcer Image to private registry") {
            steps {
                sh "docker push oussamahosni/projetdevops-backend"
            }
        }
      
    }
   
    post {
        always {
            cleanWs()
        }
    }
    
}
