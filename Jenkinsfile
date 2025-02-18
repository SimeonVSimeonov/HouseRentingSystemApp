pipeline {
  agent any
  environment {
    DOTNET_PATH = "/usr/local/share/dotnet/dotnet"
  }

  stages {
    stage ('Restore') {
      steps {
        withEnv(["PATH=${DOTNET_PATH}:/usr/sbin:/usr/bin:/sbin:/bin:$PATH"]) {
          sh '$DOTNET_PATH restore HouseRentingSystem.sln'
        }
      }
    }
    stage ('Build') {
      steps {
        withEnv(["PATH=${DOTNET_PATH}:/usr/sbin:/usr/bin:/sbin:/bin:$PATH"]) {
          sh '$DOTNET_PATH build'
        }
      }
    }
    stage ('Test') {
      steps {
        withEnv(["PATH=${DOTNET_PATH}:/usr/sbin:/usr/bin:/sbin:/bin:$PATH"]) {
          sh '$DOTNET_PATH test'
        }
      }
    }
  }
}
