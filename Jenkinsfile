
pipeline {
    agent any
    tools (nodejs "node")
    stages {

        stage('Build') {
            steps {
                sh 'npm install'
                sh 'npm run build'
            }
        }
        stage('Deployment') { 
            steps {
                azureWebAppPublish azureCredentialsId: '044bbc8b-d844-4cfb-a3ce-c92f4c39b93e',
                   resourceGroup: 'com-btr-rgp-compute-001', appName: 'com-btr-awp-compute-001',
                   filePath: '**/*.js,**/*.json,**/*.png,**/*.html,**/*.ico'
            }
        }
    }
}