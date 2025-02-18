pipeline {
    agent any
    stages {
        stage('Verify MSBuild') {
            steps {
                withEnv(["PATH=/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:$PATH"]) {
                    sh 'dotnet msbuild -version'
                }
            }
        }
        stage('Build') {
            steps {
                 withEnv(["PATH=/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:$PATH"]) {
                    sh 'dotnet restore HouseRentingSystem.sln'
                    sh 'dotnet msbuild HouseRentingSystem.sln /p:Configuration=Release'
                }
            }
        }
    }
}
