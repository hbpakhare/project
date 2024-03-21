pipeline {
		agent {
				label {
							label "built-in"
							customWorkspace "/mnt/project"
				
				}
		}
		
		environment {
						
						(url = "https://github.com/hbpakhare/project.git")
						(dev-1ip = "10.10.1.84")
						(dev-2ip = "10.10.1.219")
						(qa-1ip  = "10.10.2.105")
						(qa-2ip  = "10.10.2.38")
		
		}
		
		stages {
		
				stage ("ClONE_PROJECT"){
								
							steps {
										sh "rm -rf *"
										sh "git clone $url"
							
							}
				
				}
				
				stage ("BUILD_PROJECT") {
							
								steps {
											
											sh "cd project && mvn clean install -DskipTests=true"
								
								}
				
				}
				
				stage ("COPY") {
							
							steps {
										sh "rm -rf /mnt/wars/*"
										sh "cp -r project/target/LoginWebApp.war /mnt/wars"
							
							}
				
				
				}
				stage ("COPY_DEV_WAR") {
				
					steps {
								sh "scp -r /mnt/wars/LoginWebApp.war hrishi@${dev-1ip}:/mnt/wars"
								sh "scp -r /mnt/wars/LoginWebApp.war hrishi@${dev-2ip}:/mnt/wars"
					}
				
				}
				
				stage ("COPY_QA_WAR") {
				
					steps {
								sh "scp -r /mnt/wars/LoginWebApp.war hrishi@${qa-1ip}:/mnt/wars"
								sh "scp- r /mnt/wars/LoginWebApp.war hrishi@${qa-2ip}:/mnt/wars"
					}
				
				}
		
		
		
	}

}
