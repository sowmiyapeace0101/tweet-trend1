pipeline {
    agent {
        node{
        label 'maven'
       }
     }
stages {
        stage('clone-code') {
            steps {
            git branch: 'main', url: 'https://github.com/sowmiyapeace0101/tweet-trend1.git'
            }
        }
    }
}
