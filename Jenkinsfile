pipeline {
    agent any

    stages {
      stage('SSH transfer') {
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
                        sourceFiles: "**/*.php",
                        removePrefix: "",
                        remoteDirectory: "./home/dockeradmin/php_nginx/src",
                        execCommand: ""
                    )
                    ])
                ])
            }
        }
      }
    }
}