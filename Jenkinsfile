pipeline {
    agent any
    
    environment {
        FIRST_NAME = 'rao'
        LAST_NAME = 'talla'
    }
    
    stages {
        stage('Prepare') {
            steps {
                sh '''
                echo "firstName=${FIRST_NAME}" > build.properties
                echo "lastName=${LAST_NAME}" >> build.properties
                echo "buildTimestamp=$(date +%Y%m%d%H%M%S)" >> build.properties
                '''
            }
        }
        
        stage('Build') {
            steps {
                bat 'mvn clean package -Dproperties.file=build.properties'
            }
        }
    }
}
