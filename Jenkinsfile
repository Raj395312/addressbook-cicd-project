pipeline{
    agent any
    stages{
        stage("git clone"){
            steps{
                git 'https://github.com/Raj395312/addressbook-cicd-project'
            }
        }
        
        stage("build the package"){
            steps{
                sh 'mvn clean package'
            }
        }
        stage("docker image build"){
            steps{
                sh 'docker build -t addressbook:v1 .'
            }
        }
        stage("deploy the app"){
            steps{
                sh 'docker run -d --name addressbook -p 8081:8080 addressbook:v1'
            }
        }
    }
}
