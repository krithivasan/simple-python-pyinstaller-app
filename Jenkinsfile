pipeline {
    agent none
    stages {
        stage('Build') {
            agent {
                ecs {
                    cpu 1024
                    memory 512
                    inheritFrom 'ecs-build-farm'
                }
            }
            steps {
                sh 'Declarative pipeline is awesome'
            }
        }
    }
}
