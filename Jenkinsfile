pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('Checkout Temp Branch') {
            steps {
                git branch: 'temp',
                    url: 'https://github.com/Drft-16/DevOps.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building project...'
                sh 'ls -la'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing text files...'

                sh '''
                test -f ReadMe.txt
                test -f TempFile.txt
                test -f TestFile.txt

                echo "All files exist."
                '''
            }
        }
    }

    post {
        success {
            echo 'Build and tests passed.'
        }

        failure {
            echo 'Build or tests failed.'
        }
    }
}


