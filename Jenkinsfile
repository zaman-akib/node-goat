pipeline {
    agent any
    // environment {
    //     BLACKDUCK_TRUST_CERT=true
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
        stage("synopsys-security-scan") {
          steps {
              	echo 'SYNOPSYS SECURITY SCAN EXECUTION STARTED'

                script {
                   synopsys_scan product:'blackduck',  blackduck_url: 'https://testing.blackduck.synopsys.com/', blackduck_token: 'NjRhYTY5ZTEtY2M4ZS00YzQ5LTgwZWItMGViNTljYmYxYjc0OjNmZmQ1YzRhLTI3ZGQtNGNmMi05OTM5LWY0MTRjMzdmZjk1Mw==', blackduck_scan_full: false 
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
