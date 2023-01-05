#! groovy

pipeline {
    agent any
    environment {
    PATH = "C:\\WINDOWS\\SYSTEM32"
    GPATH = "E:\\Ruby31-x64\\bin"
    }
    stages {
      stage('Setup') {
        steps {
          echo "Setup"
          sh "brew install ruby"
          // Install bundler in order to use fastlane
          sh "gem install bundler"
          // set the local path for bundles in vendor/bundle
          sh "bundle config set --local path 'vendor/bundle'"
          // install bundles if they're not installed
          sh "bundle check || bundle install --jobs=4 --retry=3"
        }
      }

      stage('Build') {
        steps {
          echo "Building"
          sh "bundle exec fastlane build"
        }
      }

      stage('Deploy') {
              steps {
                echo "Deploying to Firebase"
                sh "bundle exec fastlane beta"
              }
      }
    }
}


