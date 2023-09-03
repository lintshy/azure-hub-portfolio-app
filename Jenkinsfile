
pipeline {
    agent any
     environment { 
                AZURE_SP = credentials('23a1e69c-1c9c-4979-a1f8-a9a822452633') 
            }
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
                azureWebAppPublish azureCredentialsId: 'd688d7cf-a868-4d53-afd5-63b64229cf75',
                   resourceGroup: 'com-btr-rgp-compute-001', appName: 'com-btr-awp-compute-001',
                   filePath: '**/*.js,**/*.json,**/*.png,**/*.html,**/*.ico'
            }
        }
    }
}