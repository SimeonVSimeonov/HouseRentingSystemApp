pipeline {
    agent any
    environment {
        PATH_EXTRA = '/usr/sbin:/usr/bin:/sbin:/bin'
        MSBUILD = "/usr/local/share/dotnet/sdk/6.0.428/MSBuild.dll"
    }
    stages {
        stage('Build') {
            steps {
             withEnv(["PATH+EXTRA=${PATH_EXTRA}"]) {
                    sh 'dotnet restore HouseRentingSystem.sln'
                    sh '$MSBUILD HouseRentingSystem.sln /p:Configuration=Release'
                 }
            }
        }
    }
}
