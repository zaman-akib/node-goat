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
                    synopsys_scan product: "POLARIS", polaris_assessment_types: "SCA,SAST", polaris_application_name: "test_jenkins", 
                     polaris_project_name: "springboot-pipeline-test", polaris_branch_name: "main", polaris_prComment_enabled: false,
                        polaris_branch_parent_name: "master", polaris_prComment_severities: "high, critical"
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
