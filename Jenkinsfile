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

            }
        }

        stage("Restore dependancies") {
            // install dependancies
            steps {
                
            }
        }

        stage("Build") {
            // build
            steps {
                
            }
        }

        stage("Run tests") {
            // run test
            steps {
                
            }
        }
    }
}