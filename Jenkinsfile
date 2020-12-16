pipeline {
    agent any
	tools{
		maven 'maven'
	}	

    stages {
        stage("build") {
            steps {
                echo 'building the application...'
				sh "mvn -B"
            }
        }

        stage("test") {
            steps {
                echo 'testing the application...'
            }
        }
        
        stage("deploy") {
            steps{
                echo 'deploying the application...'
            }
        }
    }
}