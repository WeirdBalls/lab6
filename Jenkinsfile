pipeline {
	agent any
	stages {
		stage('Checkout SCM') {
			steps {
				git clone 'https://github.com/WeirdBalls/Lab6.git'
			}
		}

		stage('OWASP DependencyCheck') {
			steps {
				dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'Default'
			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}
