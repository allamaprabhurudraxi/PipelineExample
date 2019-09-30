pipeline {
    agent any
    stages {
        /* "Build" and "Test" stages omitted */

        stage('Build') {
            steps {
                git url : 'https://github.com/allamaprabhurudraxi/springboot.git'
            }
        }

        stage('pre build step') {
            steps {
               
                sh " /opt/maven/bin/mvn sonar:sonar"

            }
        }

        stage('maven_goals_and_options') {
            steps {
                sh "/opt/maven/bin/mvn clean deploy"
            }
        }
        stage('deploy_war_file_to_tomcat_container') {
            steps {
                sh "env SERVER.PORT=8090 nohup java -jar ./target/INGSuite.jar &"

            }
        }
    }
}





