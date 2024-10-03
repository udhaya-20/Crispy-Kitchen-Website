pipeline {
	agent any
		stages {
			stage ('deploy static wesite') {
				steps {
					sh '''
						sudo cp -r * /var/www/html
					'''
					echo 'Your website deployed successfully...'
				}
			}
		}
		post {
			success {
				script {
					def ip = sh(script: "hostname -I | awk '{print $1}'", returnStdout: true).trim()
					
    					mail to: 'udhayakumarraman225@gmail.com',
         				subject: 'SUCCESS: Website deployed successfully',
         				body: "The website has been deployed successfully! You can view it at http://${ip}/"
			}
			failure {
    				mail to: 'udhayakumarraman225@gmail.com',
         			subject: 'FAILURE: Website deployment failed',
         			body: "The deployment failed. Please check the logs. \n To check your log status visit $BUILD_URL"
			}
		}
	}
