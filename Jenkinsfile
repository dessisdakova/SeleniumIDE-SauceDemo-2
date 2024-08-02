pipeline {
    agent any

    environment {
        CHROME_VERSION = "127.0.6533.89"
        CHROMEDRIVER_VERSION = "127.0.6533.8800"
        CHROME_INSTALL_PATH = "C:\\Program Files\\Google\\Chrome\\Application"
        CHROMEDRIVER_PATH = "C:\\Users\\Desi\\.nuget\\packages\\selenium.webdriver.chromedriver\\127.0.6533.8800\\driver\\win32\\chromedriver.exe"
    }
    stages {
        stage("Checkout code") {
            // checkout repository
            steps {
                git branch: 'main', url: 'https://github.com/dessisdakova/SeleniumIDE-SauceDemo-2'
            }
        }

        stage("Setup .NET Core") {
            // install dot net
            steps {
                bat '''
                echo Downloading .Net 6 SDK
                curl -l -o dotnet-sdk-6.0.132-win-x86.exe https://download.visualstudio.microsoft.com/download/pr/ad59f1d1-5f19-4474-86be-2f09ab195618/5c7a64445dae84e386bb88e1f6ac09e4/dotnet-sdk-6.0.132-win-x86.exe
                echo Installing .Net 6 SDK
                dotnet-sdk-6.0.132-win-x86.exe /quite /norestart
                '''
            }
        }

        stage("Restore dependancies") {
            // install dependancies
            steps {
                bat 'dotnet restore SeleniumIde.sln'
            }
        }

        stage("Build") {
            // build
            steps {
                bat 'dotnet build SeleniumIde.sln --configuration Release'
            }
        }

        stage("Run Tests") {
            // run test
            steps {
                bat 'dotnet test SeleniumIde.sln --logger "trx;LogFileName=TestResults.trx"'
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: '**/TestResults/*.trx', allowEmptyArchive: true
            step([
                $class: 'MSTestPublisher',
                testResultsFile: '**/TestResults/*.trx'
            ])
        }
    }
}