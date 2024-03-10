pipeline {
    agent {
    node {
         label 'maven'
    }
    }
    stages {
        stage('code-cloud') {
            steps {
                git branch: 'main', url: 'https://github.com/sowmiyapeace0101/tweet-trend1.git'
            }
        }
    }
}