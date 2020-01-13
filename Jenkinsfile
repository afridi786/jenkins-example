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
         stage ('Compile Stage') {
            steps {
               sh 'mvn clean compile'
            }
        }
        stage ('Testing Stage') {
            steps {
               sh 'mvn test'
            }
        }
        stage ('install Stage') {
            steps {
               sh 'mvn clean install'
            }
        }
	}
}
