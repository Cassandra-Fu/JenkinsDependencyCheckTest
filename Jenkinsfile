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
				dependencyCheck additionalArguments: '--noupdate --nvdApiKey e38784dc-b37b-4d03-a011-ba432b095a74 --project WORKSPACE --format XML --disableYarnAudit', odcInstallation: 'OWASP Dependency-Check Vulnerabilities'
				dependencyCheckPublisher pattern: 'dependency-check-report.xml'
			}
		}
	}	
}
