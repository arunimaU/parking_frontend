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
                    sh 'npm audit fix'
                }
            }
            stage('Deploy'){
                steps{
                    sh 'cp -r /var/jenkins_home/workspace/build /usr/local/tomcat/webapps'
                    sh 'curl -u admin:admin http://13.233.196.102:8888/manager/reload?path=/build'
                }
            }
            }
        }
