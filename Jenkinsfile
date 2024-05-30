pipeline {
    agent any
    environment {
        // BLACKDUCK_TRUST_CERT=true
        POLARIS_ACCESSTOKEN = credentials('poc-polaris-token')
    }
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
                   synopsys_scan product: "polaris",
                       polaris_server_url: "${env.POLARIS_URL}",
                       polaris_access_token: "${POLARIS_ACCESSTOKEN}"
                       polaris_assessment_types: "SCA", 
                       polaris_branch_name: "main",
                       polaris_application_name: "test_jenkins",
                       polaris_project_name: "springboot-pipeline-test"
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
