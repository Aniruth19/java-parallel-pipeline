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
                        // Absolute path to build.bat in Program1 directory
                        bat 'call "C:\\Users\\Aniruth\\Desktop\\java-parallel-pipeline\\Program1\\build.bat"'
                    }
                }
                stage('Program 2') {
                    steps {
                        // Absolute path to build.bat in Program2 directory
                        bat 'call "C:\\Users\\Aniruth\\Desktop\\java-parallel-pipeline\\Program2\\build.bat"'
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
