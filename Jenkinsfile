pipeline {
  agent any
  environment {
    DOTNET_PATH = "/usr/local/share/dotnet/dotnet"
  }

  stages {
    stage ('NPM install') {
      steps {
        withEnv(["PATH=${DOTNET_PATH}:/usr/sbin:/usr/bin:/sbin:/bin:$PATH"]) {
          sh '$DOTNET_PATH msbuild -version'
        }
      }
    }
    stage ('Run tests') {
      steps {
        withEnv(["PATH=${DOTNET_PATH}:/usr/sbin:/usr/bin:/sbin:/bin:$PATH"]) {
          sh '$DOTNET_PATH restore HouseRentingSystem.sln'
        }
      }
    }
  }
}
