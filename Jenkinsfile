pipeline {
  agent any
  environment {
    MAJOR = '1'
    MINOR = '0'
  }
  stages {
    stage ('PostBuild') {
      steps {
        UiPathTest (
          testTarget: [$class: 'TestSetEntry', testSet: "DataValidation"],
          orchestratorAddress: "https://cloud.uipath.com/",
          orchestratorTenant: "DefaultTenant",
          folderName: "Shared",
          timeout: 100000,
          traceLevel: com.uipath.uipathpackage.util.TraceLevel.Info,
          testResultsOutputPath: "result.json",
          parametersFilePath: null,
          credentials: [$class: 'UserPassAuthenticationEntry', credentialsId: "APIUserKey"]
        )
      }
    }
  }
}
