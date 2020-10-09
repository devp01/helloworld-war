pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building'
        git(changelog: true, url: 'https://github.com/devp01/helloworld-war.git', branch: 'master')
        sh 'tar -czf test_hello.tgz src/'
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
        sshPublisher(failOnError: true, publishers: [
                                                                                              sshPublisherDesc(
                                                                                                                configName: "test1",
                                                                                                                verbose: true,
                                                                                                                transfers: [
                                                                                                                                  sshTransfer(sourceFiles: "test_hello.tgz",),
                                                                                                                                  sshTransfer(execCommand: "tar -xvf test_hello.tgz")
                                                                                                                              ]
                                                                                                                          )
                                                                                                                      ])
            }
          }

        }
      }