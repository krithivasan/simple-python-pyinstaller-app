pipeline {
    agent none
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'python:2-alpine'
                }
            }
            agent {
                ecs {
                    inheritFrom 'ecs-build-farm'
                    cpu 2048
                    memory 4096
                    logDriver 'fluentd'
                    logDriverOptions([[name: 'foo', value:'bar'], [name: 'bar', value: 'foo']])
                }
            }
            steps {
                sh 'python -m py_compile sources/add2vals.py sources/calc.py'
            }
        }
    }
}
