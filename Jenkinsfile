pipeline {
    agent any

    stages {

        stage('build') {
            steps {
              bat '''
                 cd customer-service
                 ./mvnw -DskipTests clean compile
              '''
            }
        }

        stage('test') {
            steps {
              bat '''
                 cd customer-service
                     ./mvnw test
              '''
            }
        }

        stage('deliver') {
            steps {
              bat '''
                 cd customer-service
                     ./mvnw -DskipTests install
              '''
            }
        }

    }
}
