node {
      checkout scm
      stage("synopsys-security-scan") {
            synopsys_scan product: "polaris", polaris_application_name: "YOUR_POLARIS_APPLICATION_NAME", 
                     polaris_project_name: "YOUR_POLARIS_PROJECT_NAME", polaris_assessment_types: "SCA, SAST", 
                     polaris_branch_name: "POLARIS_BRANCH_NAME", polaris_prComment_enabled: true,
                     polaris_branch_parent_name: "POLARIS_BRANCH_PARENT_NAME", 
                     polaris_prComment_severities: "high, critical, medium, low, informational"
     }
}
