pipeline {
    agent any

    environment {
        CHROME_VERSION = "127.0.6533.89"
        CHROMEDRIVER_VERSION = "127.0.6533.8800"
        CHROME_INSTALL_PATH = "C:\\Program Files\\Google\\Chrome\\Application"
        CHROMEDRIVER_PATH = "C:\\Users\\Desi\\.nuget\\packages\\selenium.webdriver.chromedriver\\127.0.6533.8800\\driver\\win32\\chromedriver.exe"
    }
    stages {
        stage("") {
            // checkout repository
            steps {
                git branch: 'main', url: 'https://github.com/dessisdakova/SeleniumIDE-SauceDemo-2'
            }
        }

        stage("") {
            // install dot net
        }

        stage("") {
            // install dependancies
        }

        stage("") {
            // build
        }

        stage("") {
            // run test
        }
    }
}