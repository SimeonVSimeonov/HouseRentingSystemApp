pipeline {
  agent any
  environment {
    PATH_EXTRA = '/usr/sbin:/usr/bin:/sbin:/bin'
  }

  stages {
    stage ('NPM install') {
      steps {
        withEnv(["PATH+EXTRA=${PATH_EXTRA}"]) {
          sh 'dotnet msbuild -version'
        }
      }
    }
    stage ('Run tests') {
      steps {
        withEnv(["PATH+EXTRA=${PATH_EXTRA}"]) {
          sh 'dotnet restore HouseRentingSystem.sln'
        }
      }
    }
  }
}