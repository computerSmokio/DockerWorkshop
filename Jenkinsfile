pipeline{
    agent any
    stages{
        stage('Create docker image'){
            steps{
                checkout scm
                script{
                    app = docker.build('matiasvg2018/minecraft_server:latest')
                    docker.withRegistry('', 'docker_credentials'){
                        app.push()
                    }
                }
            }
        }
    }
}
