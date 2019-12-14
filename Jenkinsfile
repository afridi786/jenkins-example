pipeline {
    agent any


    stages {
        stage('SCM Checkout'){
          git 'https://github.com/afridi786/jenkins-example.git'
        }
  }
    {
        stage ('Compile Stage') {

            steps {
               withMaven(jdk: 'LOCAL_JDK', maven: 'LOCAL_MAVEN') { 
						sh 'mvn clean compile'
			 		}
            }
        }

        stage ('Testing Stage') {

            steps {
               withMaven(jdk: 'LOCAL_JDK', maven: 'LOCAL_MAVEN') { 
						sh 'mvn test'
			 		}
            }
        }


        stage ('install Stage') {
            steps {
               withMaven(jdk: 'LOCAL_JDK', maven: 'LOCAL_MAVEN') { 
						sh 'mvn clean install'
			 		}
            }
        }

         stage ('deploy to tomcat') {
             steps {
                 sshagent(['NewTomcatForMaven']) {
   					sh 'ssh -o StrictHostKeyChecking=no */target/*.war ec2-user@172.31.41.161:/var/lib/tomcat/webapps'
						}
             }
   }
}
}
