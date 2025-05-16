pipeline {
    agent any
    stages{
        stage('build project'){
            steps{
                git url:'https://github.com/mdikra/banking-finance.git', branch: "master"
                sh 'mvn clean package'
              
            }
        }
        stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t danishdockerhub/staragile-projectfinance:v1 .'
                    sh 'docker images'
                }
            }
        }
         
        
     stage('Deploy') {
            steps {
                sh 'sudo docker run -itd --name My-first-container-banking -p 8124:8081 danishdockerhub/staragile-projectfinance:v1'
                  
                }
            }
        
    }
}
