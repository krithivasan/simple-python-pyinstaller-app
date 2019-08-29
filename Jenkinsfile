pipeline {
    agent none
    stages {
        stage('Build') {
            agent {
                label 'ecs-build-farm'
                /*ecs {
                    cpu 1024
                    memory 512
                    inheritFrom 'ecs-build-farm'
                }*/
            }
            steps {
                sh 'echo The user is $USER'
            }
        }
    }
}
