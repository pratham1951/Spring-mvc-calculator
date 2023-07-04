pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "MAVEN_HOME"
    }

    stages {
        stage('Checkout Code') {
            steps {
                // Get some code from a GitHub repository
//                 git 'https://github.com/pratham1951/SpringMVC-calculator.git'
		    checkout scm

            }
		}	
	    stage('Build') {
            steps {
               
               // To run Maven on a Windows agent, use
                bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }
		}	
	    stage('Test') {
            steps {
               

                // To run Maven on a Windows agent, use
                bat "mvn -Dmaven.test.failure.ignore=true clean test"
            }	
		}
		stage('Junit Test Results') {
		    steps {
		        junit 'target/surefire-reports/*.xml'
		        
		    }
		}

        }
    }
