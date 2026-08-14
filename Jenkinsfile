pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Validate Compose') {
            steps {
                sh '''
                    set -e

                    for dir in docker/*; do
                        if [ -f "$dir/compose.yml" ]; then
                            echo "Validating $dir"
                            docker compose -f "$dir/compose.yml" config -q

                        elif [ -f "$dir/compose.yaml" ]; then
                            echo "Validating $dir"
                            docker compose -f "$dir/compose.yaml" config -q
                        fi
                    done
                '''
            }
        }

        stage('Detect Changes') {
            steps {
                sh '''
                    echo "Changed files:"
                    git diff --name-only HEAD~1 HEAD || true
                '''
            }
        }

        stage('Docker Status') {
            steps {
                sh 'docker ps'
            }
        }
    }
}
