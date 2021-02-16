pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                sh "mvn clean package"
            }
        }
        stage("Deployment"){
            steps{
                deploy adapters: [tomcat7(credentialsId: 'ee3fc4df-1042-4ca6-a0d8-e76d1ebb64b5', 
                path: '',
                url: 'http://ec2-65-0-135-74.ap-south-1.compute.amazonaws.com:8080/')], 
                contextPath: 'javawebapp', 
                war: '**/demo-java-webapp-project.war'
            }
        }
    }
}
