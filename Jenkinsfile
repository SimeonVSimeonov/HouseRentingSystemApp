pipeline {
    agent any
    stages {
        stage('Verify MSBuild') {
         withEnv(["PATH=/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:$PATH"]) {
                steps {
                    sh 'dotnet msbuild -version'
                }
            }
        }
        stage('Build') {
         withEnv(["PATH=/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:$PATH"]) {
                steps {
                    sh 'dotnet restore HouseRentingSystem.sln'
                    sh 'dotnet msbuild HouseRentingSystem.sln /p:Configuration=Release'
                }
            }
        }
    }
}
