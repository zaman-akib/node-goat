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
        stage("synopsys-security-scan") {
           steps {
               echo 'SYNOPSYS SECURITY SCAN STARTED'
               script {
                   blackduck_scan product: "blackducksca", detect_scan_full: true
                       // polaris_server_url: "${BRIDGE_POLARIS_SERVERURL}",
                       // polaris_access_token: "${BRIDGE_POLARIS_ACCESSTOKEN}",
                       // polaris_assessment_types: "SCA",
                       // polaris_application_name: "test_jenkins",
                       // polaris_project_name: "test_jenkins"
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
