pipeline {
    agent any
	tools{
		jdk 'LOCAL_JDK'
		maven 'LOCAL_MAVEN' 
	}

    stages {
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
