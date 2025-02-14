pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git url: 'https://github.com/Aniruth19/java-parallel-pipeline.git', branch: 'main'
            }
        }

        stage('Run Java Programs in Parallel') {
            parallel {
                stage('Program 1') {
                    steps {
                        bat 'Program1\\build.bat'
                    }
                }
                stage('Program 2') {
                    steps {
                        bat 'Program2\\build.bat'
                    }
                }
            }
        }
    }

    post {
        success {
            echo "🎯 Both Java programs executed successfully!"
        }
        failure {
            echo "❌ Build failed! Check logs."
        }
    }
}
