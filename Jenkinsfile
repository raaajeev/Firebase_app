#! groovy

pipeline {
    agent any
    environment {
    PATH = "E:\\Ruby31-x64\\bin"
    //HOME_PATH = "E:\\Ruby31-x64\\bin"
    }
    stages {
//       stage('Setup') {
//         steps {
//           echo "Setup"
//           // Install bundler in order to use fastlane
//           bat "gem install bundler"
//           // set the local path for bundles in vendor/bundle
//           bat "bundle config set --local path 'vendor/bundle'"
//           // install bundles if they're not installed
//           bat "bundle check || bundle install --jobs=4 --retry=3"
//         }
//       }

      stage('Build') {
        steps {
          echo "Building"
          bat "fastlane build"
        }
      }

      stage('Deploy') {
              steps {
                echo "Deploying to Firebase"
                bat "fastlane beta"
              }
      }
    }
}

