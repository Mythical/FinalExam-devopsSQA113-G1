pipeline {
    agent any

    environment {
        FIREBASE_TOKEN = '1//06PGs684XgZeOCgYIARAAGAYSNwF-L9IrZ0yYVU9w_NvX7oy9n2hcbi_uhTd7e3Dwyz31-i4w84BzsIepRkmE5VcOVSkPiqWxo2Q'
    }

    stages {
        stage('Install Firebase Tools') {
            steps {
                sh 'npm install -g firebase-tools'
            }
        }

        stage('Deploy to Testing') {
            steps {
                sh 'firebase use testing --token $FIREBASE_TOKEN'
                sh 'firebase deploy --only hosting --token $FIREBASE_TOKEN'
            }
        }

        stage('Deploy to Staging') {
            steps {
                sh 'firebase use staging --token $FIREBASE_TOKEN'
                sh 'firebase deploy --only hosting --token $FIREBASE_TOKEN'
            }
        }

        stage('Deploy to Production') {
            steps {
                sh 'firebase use production --token $FIREBASE_TOKEN'
                sh 'firebase deploy --only hosting --token $FIREBASE_TOKEN'
            }
        }
    }
}
