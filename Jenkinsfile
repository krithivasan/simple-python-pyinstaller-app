pipeline {
    agent none
    stages {
        stage('Build') {
            agent {
                ecs {
                    cloud 'ecs-build-farm'
                    inheritFrom 'ecs-build-farm'
                }
            }
            steps {
                sh 'python -m py_compile sources/add2vals.py sources/calc.py'
            }
        }
    }
}
