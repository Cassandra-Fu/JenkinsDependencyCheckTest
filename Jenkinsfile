pipeline {
	agent any
	stages {
		stage('Checkout SCM') {
			steps {
				git(url: 'https://github.com/Cassandra-Fu/JenkinsDependencyCheckTest.git', branch: 'master')
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
