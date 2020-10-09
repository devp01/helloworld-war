pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building'
        git(changelog: true, url: 'https://github.com/devp01/helloworld-war.git', branch: 'master')
        sh '''tar -czf /tmp/test_hello.tgz src/
'''
        echo 'done'
      }
    }

    stage('Test') {
      steps {
        echo 'Testing'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying'
      }
    }

  }
}