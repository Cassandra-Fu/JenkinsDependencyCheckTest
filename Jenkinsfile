pipeline {
	agent any
	stages {
		stage('Checkout SCM') {
			steps {
				git '/home/student20/vulnerableWebApp/JenkinsDependencyCheckTest'
			}
		}

		stage('OWASP DependencyCheck') {
			steps {
				//dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'Default'
				dependencyCheck additionalArguments: '--project WORKSPACE', odcInstallation: 'OWASP Dependency-Check Vulnerabilities'
				dependencyCheckPublisher pattern: 'dependency-check-report.xml'
			}
		}
	}	
}
