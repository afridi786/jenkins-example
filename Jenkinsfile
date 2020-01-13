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
               sh 'mvn clean test'
            }
        }


        stage ('Deployment Stage') {
            steps {
                sh 'mvn deploy'
            }
        }
    }
}
