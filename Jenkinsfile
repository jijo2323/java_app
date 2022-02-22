pipeline{
    agent any
    
    tools{
        maven "Maven"
    }
    stages{
        stage('Git Clone'){
            steps{
                git branch: 'main', credentialsId: 'my-github-credentials', url: 'https://github.com/jijo2323/java_app.git'
            }
        }
        
        stage('Build'){
            steps{
                sh "mvn clean install"
            }
        }
        
        
    }
}
