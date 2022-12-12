pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out from SCM'
	        checkout changelog: false, poll: false,
		scm: [$class: 'GitSCM',
		branches: [[name: '*/master']],
		extensions: [], userRemoteConfigs: [[credentialsId: 'git',
		url: 'https://github.com/dkakandki/hello-world.git']]]	
            }
        }
        stage('BUILD + UT') {
            steps {
                echo 'Building and Testing'
		sh 'mvn clean compile package'
            }

        }
        stage('deploy') {
            steps {
                echo 'deploy....'
		//sh 'mvn deploy'
            }
        }
    }
    }
