pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Show Commit') {
            steps {
                sh '''
                    echo "Commit:"
                    git log -1 --oneline
                '''
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

        stage('Docker Status') {
            steps {
                sh 'docker ps'
            }
        }
    }
}
