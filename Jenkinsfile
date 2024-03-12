pipeline {
  environment {
    registry = "umairshah379/mydockerrepo"
    credentialsId = 'umairshah379'
    dockerImage = ''
  }
  agent any
  stages {
    stage('Cloning Git') {
      steps {
        git 'https://github.com/umairshah124/docker_jen.git'

      }
    }
    stage('Building image') {
      steps{
        script {
           dockerImage = docker.build registry + ":$BUILD_NUMBER"
        }
      }
    }
    stage('Push docker image'){
            steps{
                script{
                    withCredentials([string(credentialsId: 'umairshah379', variable: 'dockervariable')]) {
                        sh 'docker login -u umairshah379 -p ${dockervariable}'
                        sh 'docker push umairshah379/mydockerrepo:0.0.Realease'			}
		}
	}	
	}
}
}
