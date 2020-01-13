pipeline {
    agent any
	tools{
		jdk 'LOCAL_JDK'
		maven 'LOCAL_MAVEN' 
	}

    stages {
        stage('SCM Checkout'){
		 steps{
          git 'https://github.com/afridi786/jenkins-example.git'
			}
	}
        stage ('Testing Stage') {
            steps {
               sh 'mvn validate'
            }
        }
        stage ('install Stage') {
            steps {
               sh 'mvn clean install'
            }
        }
	}
}
