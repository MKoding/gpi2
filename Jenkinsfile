pipeline {
    agent any
    stages {
        stage('Gradle') {
            steps {
                sh 'ls'
                sh 'cd /home/alumno/gpi2/ejercicio_3_practica_build_1/GPI-II/'
                sh './gradlew'
            }
        }
        stage('Arduino') {
            steps {
                sh 'cd /home/alumno/gpi2/ejercicio_3_practica_build_1/MyArduinoProject/src/FooProject/'
                sh 'arduino-cli compile --fqbn arduino:avr:nano'
            }       
        }
        stage('Maven') {
            steps {
                sh 'cd /home/alumno/gpi2/ejercicio_4_practica_build_2/example-webapp/'
                sh 'mvn -B -DskipTests clean package'
                sh 'mvn test'
                sh './jenkins/scripts/deliver.sh'
            }
        }
    }
}
