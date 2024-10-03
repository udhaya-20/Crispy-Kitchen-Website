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
				mail to: 'udhayakumarraman225@gmail.com',
         			subject: 'SUCCESS: Website deployed successfully',
         			body: "The deployment was successfull'
			}
			failure {
    				mail to: 'udhayakumarraman225@gmail.com',
         			subject: 'FAILURE: Website deployment failed',
         			body: "The deployment failed. Please check the logs. To check your log status visit $BUILD_URL"
			}
		}
	}
