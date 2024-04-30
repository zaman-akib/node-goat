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
               echo 'SYNOPSYS SECURITY SCAN STARTED'
               script {
                   synopsys_scan 
                       product: "polaris"
                       //polaris_server_url: "POLARIS_SERVER_URL"
                       //polaris_access_token: "POLARIS_TOKEN"
                       polaris_assessment_types: "SAST,SCA" // Accepts Multiple Values
                       polaris_branch_name: "master"
                       //polaris_application_name: "test_jenkins"
                       //polaris_project_name: "springboot-pipeline-test"
                       polaris_prComment_enabled: true 
                       //polaris_prComment_severities: 'CRITICAL,HIGH' // Accepts Multiple Values
                       //polaris_branch_parent_name: "POLARIS_PARENT_BRANCH_NAME"
                       //github_token: "GITHUB_TOKEN" // Mandatory when polaris_prComment_enabled is set to 'true' for  GitHub
                       //gitlab_token: "GITLAB_TOKEN" // Mandatory when polaris_prComment_enabled is set to 'true' for GitLab
                       //bitbucket_token: "BITBUCKET_TOKEN" // Mandatory when polaris_prComment_enabled is set to 'true' for BitBucket
                       //include_diagnostics: true
                       polaris_reports_sarif_create: true
                       //polaris_reports_sarif_groupSCAIssues: true // By default true
                       //polaris_reports_sarif_file_path: "/Users/tmp/report.sarif.json" // File path including file name where SARIF report should be created
                       //polaris_reports_sarif_severities: "CRITICAL,HIGH" // Accepts Multiple Values
                       //polaris_reports_sarif_issue_types: "SAST,SCA" // Accepts Multiple Values
                       
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
