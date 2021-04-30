pipeline {
    agent any
    stages {
        stage('Gradle') {
            steps {
                sh './ejercicio_3_practica_build_1/GPI-II/gradlew'
            }
        }
        stage('Arduino') {
            steps {
                sh 'arduino-cli compile --fqbn arduino:avr:nano ejercicio_3_practica_build_1/MyArduinoProject/src/FooProject/'
            }       
        }
        stage('Maven') {
            steps {
                sh 'mvn -B -DskipTests clean package ejercicio_4_practica_build_2/example-webapp/'
                sh 'mvn test'
                sh './jenkins/scripts/deliver.sh'
            }
        }
    }
}
