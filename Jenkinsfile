
pipeline {
    agent any
    tools {nodejs "node"}
    stages {

        stage('Build') {
            steps {
                sh 'npm install'
                sh 'npm run build'
            }
        }
        stage('Deployment') { 
            steps {
                azureWebAppPublish azureCredentialsId: '23a1e69c-1c9c-4979-a1f8-a9a822452633',
                   resourceGroup: 'com-btr-rgp-compute-001', appName: 'com-btr-awp-compute-001',
                   filePath: '**/*.js,**/*.json,**/*.png,**/*.html,**/*.ico'
            }
        }
    }
}