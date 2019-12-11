pipeline {
    agent any

    stages {

        stage('build') {
            steps {
              bat '''
                 cd customer-service
                 ./mvnw -DskipTests clean compile
                 cd ..
                 cd config-server
                 ./mvnw clean compile
                 cd ..
                 cd eureka-registry-server
                 ./mvnw clean compile
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
                 cd ..
                 cd config-server
                 ./mvnw install
                 cd ..
                 cd eureka-registry-server
                 ./mvnw install
              '''
            }
        }

    }
}
