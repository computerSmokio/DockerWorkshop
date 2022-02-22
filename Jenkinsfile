pipeline{
    agent any
    stages{
        stage('Create docker image'){
            steps{
                checkout scm
                script{
                    app = docker.build('matiasvg2018/minecraft_server:latest')
                    docker.withRegistry('', 'dockerCredentials'){
                        app.push()
                    }
                }
            }
        }
    }
}
