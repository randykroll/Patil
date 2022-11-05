pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
    }

       
    stages {
        // Specify various stage with in stages

        // stage 1. Build
        stage ('Build'){
            steps {
                sh 'mvn clean install package'
            }
        }

        // Stage2 : Testing
        stage ('Test'){
            steps {
                echo ' testing......'

            }
        }

        // Stage3 : Publish to Nexus
        stage ('Publish to Nexus'){
            steps {
                echo ' Source code published to Sonarqube for SCA......'
                nexusArtifactUploader artifacts: [[artifactId: 'VinayDevOpsLab', 
                classifier: '', 
                file: 'target/VinayDevOpsLab-0.0.4-SNAPSHOT.war', 
                type: 'war']], 
                credentialsId: '63bfdc12-a8b4-41bb-97b8-bc317a998c48', 
                groupId: 'com.vinaysdevopslab', 
                nexusUrl: '172.20.10.82:8081', 
                nexusVersion: 'nexus3', 
                protocol: 'http', 
                repository: 'VinaysDevOpsLab-SNAPSHOT', 
                version: '0.0.4-SNAPSHOT'
            }
        }
        
    }

}