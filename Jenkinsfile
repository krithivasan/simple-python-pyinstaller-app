pipeline {
    agent none
    stages {
        stage('Build') {
            agent {
                ecs {
                    cpu 1024
                    memory 512
                    image 'qnib/pytest'
                    inheritFrom 'ecs-build-farm'
                }
            }
            steps {
                sh 'py.test --verbose --junit-xml test-reports/results.xml sources/test_calc.py'
            }
            post {
                always {
                    junit 'test-reports/results.xml'
                }
            }
        }
    }
}
