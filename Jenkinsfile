pipeline {
    agent any
    // environment {
        // BLACKDUCK_TRUST_CERT=true
        // BRIDGE_POLARIS_SERVERURL = 'https://poc.polaris.synopsys.com'
        // BRIDGE_POLARIS_ACCESSTOKEN = credentials('poc-polaris-token')
    // }
    stages {
        stage("unit-test") {
            steps {
                echo 'UNIT TEST EXECUTION STARTED'
            }
        }
        stage("functional-test") {
            steps {
                echo 'FUNCTIONAL TEST EXECUTION STARTED'
            }
        }
        stage('Polaris Analysis') {
            steps {
                polaris arguments: 'analyze', polarisCli: 'CoP'
            }
        }
        stage('Polaris Issue Check') {
            steps {
                polarisIssueCheck()
            }
        }
        stage("build") {
            steps {
                echo 'BUILD EXECUTION STARTED'
                echo 'Pulling...' + env.BRANCH_NAME
            }
        }
    }
}
