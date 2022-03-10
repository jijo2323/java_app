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
        
        stage('SonarQube'){
            environment{
                scannerHome = tool 'Sonar'
            }
            steps{
                withSonarQubeEnv('SonarServer'){
                    sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=java_maven -Dsonar.sources=. -Dsonar.java.binaries=target/classes/com/mycompany/app/ " 
                }

            }
        }
        
        
    }
}
