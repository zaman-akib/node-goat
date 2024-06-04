node {
      checkout scm
      stage("synopsys-security-scan") {
        synopsys_scan product: "polaris", 
        polaris_application_name: "test_jenkins", 
        polaris_project_name: "springboot-pipeline-test",
        polaris_assessment_types: "SCA, SAST", 
        polaris_prComment_enabled: true,
        polaris_prComment_severities: "high, critical, medium, low, informational",
        // polaris_branch_name: "main",
        // polaris_branch_parent_name: "master",

        polaris_assessment_mode: "SOURCE_UPLOAD",
        project_directory: "/home/maruf/nodegoat",
        project_source_archive: "/home/maruf/nodegoat.zip",
        project_source_excludes: ".git, .gitignore"
      }
}
