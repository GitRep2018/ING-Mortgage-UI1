pipeline {

    agent any 

    tools {nodejs "NODEJS"} // NODEJS is the variable which is mentioned in global tool configurations

    stages {

        stage('checkout') { 

            steps {

                git url:'https://github.com/GitRep2018/ING-Mortgage-UI1.git'

            }

        }

        
          stage('Build') { 

            steps {

                sh '''

                npm install

                npm run build

            '''

            }

        }
  stage('Deploy') { 

            steps {

                sh '''

                cd /var/lib/jenkins/workspace/pipeline

                chmod -R 777 build/

                cp -rf build/ /opt/apache-tomcat-9.0.26/webapps/

            '''

            }

        }

    }

}
