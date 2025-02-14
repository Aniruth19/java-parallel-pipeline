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
                        // Use pushd/popd to change to the directory and cmd /c to run the batch file.
                        bat 'pushd "C:\\Users\\Aniruth\\Desktop\\java-parallel-pipeline\\Program1" && cmd /c build.bat && popd'
                    }
                }
                stage('Program 2') {
                    steps {
                        bat 'pushd "C:\\Users\\Aniruth\\Desktop\\java-parallel-pipeline\\Program2" && cmd /c build.bat && popd'
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
