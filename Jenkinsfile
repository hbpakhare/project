pipeline {

	agent {
				label {
					
						label "built-in"
						customWorkspace "/mnt/wars"
				
				}
	}
	
	environment {
						
						dev-1ip = "10.10.1.84"
						dev-2ip = "10.10.1.219"
						qa-1ip  = "10.10.2.105"
						qa-2ip  = "10.10.2.38"
		
		}
	
	stages {
	
				stage ("COPY_DEV_WAR") {
				
					steps {
								sh "scp -r LoginWebApp.war hrishi@${dev-1ip}:/mnt/wars"
								sh "scp -r LoginWebApp.war hrishi@${dev-2ip}:/mnt/wars"
					}
				
				}
				
				stage ("COPY_QA_WAR") {
				
					steps {
								sh "scp -r LoginWebApp.war hrishi@${qa-1ip}:/mnt/wars"
								sh "scp- r LoginWebApp.war hrishi@${qa-2ip}:/mnt/wars"
					}
				
				}
		
		
		
	}

}
