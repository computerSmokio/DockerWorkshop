pipeline{
    agent any
    stages{
        stage('Create docker image'){
            steps{
                checkout scm
                script{
                    app = docker.build("minecraft_server")
                    docker.withRegistry('docker/minecraft', 'dockerCredentials'){
                        app.push()
                    }
                }
            }
        }
    }
}
