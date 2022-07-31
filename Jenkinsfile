pipeline {
    agent any

    stages {
        stage('Restore') {
            steps {

                sh "dotnet restore"

            }
        }

        stage('Build') {
            steps {
                
                sh "dotnet build"

            }
        }

        stage('Test') {
            steps {
                
                sh "dotnet test"

            }

        }

       
        stage('Package') {
            steps {
                
                sh "dotnet publish"

            }

            post {
                success {
                    archiveArtifacts artifacts: 'bin/Debug/net6.0/pipelines-dotnet-core.dll', followSymlinks: false
       
                }
            }
        }
          
    }
}