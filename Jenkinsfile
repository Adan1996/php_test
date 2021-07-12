pipeline {
    agent any

    stages {
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
                        sourceFiles: "./index.php",
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