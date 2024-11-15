pipeline {
    agent any
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
        stage("black-duck-security-scan") {
           steps {
               echo 'BLACK DUCK SECURITY SCAN STARTED'
               script {
                   security_scan product: "blackducksca", blackducksca_reports_sarif_create: true, blackducksca_prComment_enabled: true
                }
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
