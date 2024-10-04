pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/kunal5144/Health-care1-project'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with Kunal'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with Kunal'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with Kunal'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with Kunal'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t myimg1 .'
           }
         }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8082:8082 --name c000 myimg1'
            }
        }   
    }
}
