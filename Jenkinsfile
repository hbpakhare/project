pipeline {
		agent {
				label {
							label "built-in"
							customWorkspace "/mnt/project"
				
				}
		}
		
		environment {
						
						url = "https://github.com/hbpakhare/project.git"
		
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
		
		
		
		}

}
