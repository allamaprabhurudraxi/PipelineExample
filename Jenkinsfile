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
                deploy adapters: [tomcat9(credentialsId: '93dcbd52-a3a3-4808-b8e3-8b301ad390db',
                                      path: '', url: 'http://18.224.64.187:8090/')], 
                    contextPath: '/demo', onFailure: false, jar: '**/*.jar'

            }
        }
    }
}





