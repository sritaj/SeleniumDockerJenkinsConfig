pipeline{
    agent any
    stages{
        stage("Start Grid"){
            steps{
                sh "docker-compose up -d hub chrome firefox"
            }
        }
        stage("Run Test"){
            steps{
                sh "docker-compose up flight-details-test-module registration-confimration-test-module user-registration-test-module"
            }
        }
    }
    post{
        always{
           // archiveArtifacts artifacts: 'output/**'
			sh "docker-compose down"
			//sh "sudo rm -rf output/"
        }
    }
}