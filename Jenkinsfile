pipeline {
    agent none
    stages {
        stage('Build') {
            agent {
                ecs {
                    cpu 1024
                    memory 512
                    inheritFrom 'ecs-build-farm'
                    label 'ecs-build-farm'
                    image 'python:2-alpine'
                }
            }
            steps {
                sh 'python -m py_compile sources/add2vals.py sources/calc.py'
            }
        }
    }
}
