pipeline {
	agent {
		docker {
			image 'composer:latest'
		}
	}
	stages {
		stage('Redirect to Lab 7 Branch') {
            steps {
                script {
                    git branch: "lab7",
                        url: "https://github.com/farhanhan1/JenkinsDependencyCheckTest.git"
                }
            }
		}
		stage('Build') {
			steps {
				sh 'composer install'
			}
		}
		stage('Test') {
			steps {
                sh './vendor/bin/phpunit tests'
            }
		}
	}
}