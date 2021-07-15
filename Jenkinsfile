pipeline {
    agent any

    stages {
      stage('Build') {
          steps {
              echo 'This is build steps'
          }
      }

      stage('Test') {
          steps {
              echo 'This is test steps'
          }
      }

      stage('Deploy on Dev') {
        steps {
            script {
                sshPublisher(
                continueOnError: false, failOnError: true,
                publishers: [
                    sshPublisherDesc(
                    configName: "docker-host",
                    verbose: true,
                    transfers: [
                    sshTransfer(
                        sourceFiles: "**/index.php",
                        removePrefix: "",
                        remoteDirectory: "./php_nginx/src/php_nginx",
                        execCommand: ""
                    )
                    ])
                ])
            }
        }
      }
    }
}