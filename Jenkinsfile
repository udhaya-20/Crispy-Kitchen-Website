pipeline {
	agent any
		stages {
			stage ('deploy static wesite') {
				steps {
					sh '''
						cp -r * /var/www/html
					'''
					echo 'Your website deployed successfully...'
				}
			}
		}
		post {
			success {
				echo 'SUCCESS: The website has been deployed successfully!'
				
				mail to: 'udhayakumarraman225@gmail.com',
         			subject: 'SUCCESS: Website deployed successfully',
         			body: 'The deployment was successfull'
			}
			failure {
				echo 'FAILURE: The website deployment failed!'
				
    				mail to: 'udhayakumarraman225@gmail.com',
         			subject: 'FAILURE: Website deployment failed',
         			body: "The deployment failed. Please check the logs.\nTo check your log status visit ${BUILD_URL}"
			}
		}
	}
