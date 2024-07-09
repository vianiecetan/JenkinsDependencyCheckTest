pipeline {
	agent any
	stages {
		// stage('Checkout SCM') {
		// 	steps {
		// 		git '/home/JenkinsDependencyCheckTest'
		// 	}
		// }

		stage('OWASP DependencyCheck') {
			steps {
				dependencyCheck additionalArguments: '-n --noupdate --format HTML --format XML', odcInstallation: 'OWASP Dependency-Check Vulnerabilities'
			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}