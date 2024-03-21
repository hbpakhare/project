pipeline {

	agent {
				label {
					
						label "built-in"
						customWorkspace "/mnt/wars"
				
				}
	}
	
	environment {
						
						dev1ip = "10.10.1.84"
						dev2ip = "10.10.1.219"
						qa1ip  = "10.10.2.105"
						qa2ip  = "10.10.2.38"
		
		}
	
	stages {
	
				stage ("COPY_DEV_WAR") {
				
					steps {
								sh "scp -r LoginWebApp.war hrishi@${dev1ip}:/mnt/wars"
								sh "scp -r LoginWebApp.war hrishi@${dev2ip}:/mnt/wars"
					}
				
				}
				
				stage ("COPY_QA_WAR") {
				
					steps {
								sh "scp -r LoginWebApp.war hrishi@${qa1ip}:/mnt/wars"
								sh "scp -r LoginWebApp.war hrishi@${qa2ip}:/mnt/wars"
					}
				
				}
		
		
		
	}

}
