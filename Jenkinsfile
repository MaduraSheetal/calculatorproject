pipeline {
    agent any
	tools{
		maven 'maven'
	}	

    stages {
        stage("build") {
            steps {
                echo 'building the application...'
				sh "mvn -B clean"
            }
        }

        stage("test") {
            steps {
                echo 'testing the application...'
				sh "mvn integration-test"
            }
        }
        
        stage("deploy") {
            steps{
                echo 'deploying the application...'
            }
        }
    }
	post{
		always{
			echo 'this will always run'
			junit '**/target/surefire-reports/TEST-*.xml'
		}
		success{
			echo 'this will run only if successfull'
		}
		failure{
			echo 'This will run only if failed'
		}
		unstable{
			echo 'This will run only if the run was unstable'
		}
		changed{
			echo 'This will run only if the state changed'
		}
}
}