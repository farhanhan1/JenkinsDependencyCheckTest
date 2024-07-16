pipeline {
	agent any
	stages {
		stage('Checkout SCM') {
            steps {
                script {
                    git branch: "master",
                        url: "https://github.com/farhanhan1/JenkinsDependencyCheckTest.git"
                }
            }
		}

		stage('OWASP DependencyCheck') {
			steps {
				dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: '/var/jenkins_home/tools/org.jenkinsci.plugins.DependencyCheck.tools.DependencyCheckInstallation/OWASP_Dependency-Check_Vulnerabilities/dependency-check'
			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}