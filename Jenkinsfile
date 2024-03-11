pipeline {
    agent { label 'maven' }

    environment {
        PATH = "/opt/apache-maven-3.9.6/bin:$PATH"
    }

    stages {
        stage("Build") {
            steps {
                echo "------- build started --------"
                sh 'mvn clean deploy -Dmaven.test.skip=true'
                echo "---------build completed ----------"
            }
        }

        stage("Test") {
            steps {
                echo "--------unit test started ---------"
                sh 'mvn surefire-report:report'
                echo "---------unit test completed -------"
            }
        }

        stage('SonarQube analysis') {
            environment {
                scannerHome = tool 'sonar-scanner' // Sonar scanner name should match the one defined in the tools
            }
            steps {
               
                    withSonarQubeEnv('sonnar-cloud') {
                        sh "${scannerHome}/bin/sonar-scanner" // Communicate with SonarQube server and send analysis report
                    }
                }
           }
    }
}