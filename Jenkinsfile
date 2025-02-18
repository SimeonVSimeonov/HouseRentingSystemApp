pipeline {
    agent any
    environment {
        MSBUILD = "/usr/local/share/dotnet/sdk/6.0.428/MSBuild.dll"
    }
    stages {
        stage('Build') {
            steps {
                sh 'dotnet restore HouseRentingSystem.sln'
                sh '$MSBUILD MyProject.sln /p:Configuration=Release'
            }
        }
    }
}
