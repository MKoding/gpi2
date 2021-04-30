pipeline {
    agent any
    stages {
        stage('Gradle') {
            steps {
                sh 'cd ejercicio_3_practica_build_1/GPI-II/'
                sh 'ls'
                sh './gradlew'
                sh 'cd ..'
            }
        }
        stage('Arduino') {
            steps {
                sh 'cd MyArduinoProject/src/FooProject/'
                sh 'arduino-cli compile --fqbn arduino:avr:nano'
                sh 'cd ../../../..'
            }       
        }
        stage('Maven') {
            steps {
                sh 'cd /ejercicio_4_practica_build_2/example-webapp/'
                sh 'mvn -B -DskipTests clean package'
                sh 'mvn test'
                sh './jenkins/scripts/deliver.sh'
            }
        }
    }
}
