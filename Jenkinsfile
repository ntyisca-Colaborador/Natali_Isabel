pipeline {
    agent any
    stages {
        stage('Clonar Código') {
            steps {
                checkout scm
            }
        }
        stage('Ejecutar Pruebas Python') {
            steps {
                // Contenedor efímero de Python para evaluar el script
                sh 'docker run --rm --volumes-from jenkins -w $WORKSPACE python:3.11-slim python -m unittest test_app.py'
            }
        }
    }
}