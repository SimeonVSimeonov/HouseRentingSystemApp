pipeline {
    agent any
    environment {
        PATH_EXTRA = '/usr/sbin:/usr/bin:/sbin:/bin'
    }
    stages {
        stage('Verify MSBuild') {
            steps {
                sh 'dotnet msbuild -version'
            }
        }
        stage('Build') {
            steps {
                sh 'dotnet restore HouseRentingSystem.sln'
                sh 'dotnet msbuild HouseRentingSystem.sln /p:Configuration=Release'
            }
        }
    }
}
