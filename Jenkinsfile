pipeline {
    agent any
    stages {
        /* "Build" and "Test" stages omitted */

        stage('Build') {
            steps {
                git url : 'https://github.com/allamaprabhurudraxi/springboot.git'
            }
        }


        stage('maven_goals_and_options') {
            steps {
                sh "sudo /opt/maven/bin/mvn clean deploy sonar:sonar"
            }
        }
        
        stage('deploy_war_file_to_tomcat_container') {
            steps {
                sh "sudo java -jar $WORKSPACE/target/INGSuite.jar"

            }
        }
    }
}
