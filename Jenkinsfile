pipeline {
	  agent any
	  stages {
	     stage("Cleaning stage") {
		steps {
		  bat "mvn clean"
		}
	    }	
		
	   stage("Testing stage") {
	      steps {
		  bat "mvn test"
		}
	   }
		  
	   stage("Package stage") {
	      steps {
	         bat "mvn package"
                  }
	   }	
           stage("Consolidate Results") {
	      steps {
					input ("Do you want to capture results?")
					junit '**/target/surefire-reports/TEST-*.xml'
					archive 'target/*.jar'
				}			
		    }
		
	    }
    }
