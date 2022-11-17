pipeline{
    agent{
        label "nodejs"
    }
    stages{
        stage("Install dependencies"){
            steps{
                sh "npm ci"
            }
        }

        stage("Check Style"){
            steps{
                sh "npm run lint"
            }
        }

        stage("Test"){
            steps{
                sh "npm test"
            }
        }

        // Add the Release stage here new

	stage('Release') {

		steps {

		sh '''

		oc project usergreet

		oc start-build greeting-console --follow --wait

		'''

		}

	}

    }
}
