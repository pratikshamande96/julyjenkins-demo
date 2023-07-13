pipeline {
    agent any
    tools {nodejs "mynodejs"}
    environment {
        NODE_ENV= "production"
    }
    stages {
        stage('build') {
            environment{
                NODE_ENV= "develop"
            }
            steps {
                echo NODE_ENV
                git 'https://github.com/pratikshamande96/julyjenkins-demo.git'
                echo 'The content of this file is'
                sh 'cat jenkinsdemo.txt'
            }
        }
            stage('Prod') {
            steps {
                echo NODE_ENV
                sh 'npm install'
            }
        }
                    stage('myartifact') {
            steps {
            archiveArtifacts artifacts: '**', followSymlinks: false
            }
        }
    }
}
