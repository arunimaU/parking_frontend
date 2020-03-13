pipeline {
    agent any
        stages{
            stage('Git Checkout'){
                steps{
                    git 'https://github.com/arunimaU/parking_frontend/'
                }
            }
            stage('Build') {
                steps{
                    sh 'npm install'
                    sh 'npm run build'
             
                }
            }
            stage('Deploy'){
                steps{
                    sh 'cp -r $WORKSPACE/build /opt/apache-tomcat-9.0.31/webapps'
                    sh 'curl -u admin:admin http://13.127.197.181:8888/manager/reload?path=/build'
                }
            }
            }
        }
