node {
      checkout scm
      stage("synopsys-security-scan") {
            synopsys_scan product: "polaris", polaris_application_name: "test_jenkins", 
                     polaris_project_name: "springboot-pipeline-test", polaris_assessment_types: "SCA, SAST", 
                     polaris_branch_name: "main", 
                     polaris_branch_parent_name: "master", 
                     polaris_prComment_severities: "high, critical"
     }
}
