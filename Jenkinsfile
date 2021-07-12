pipeline {
    agent any

    stages {
        stage('SSH transfer') {
            script {
            sshPublisher(
            continueOnError: false, failOnError: true,
            publishers: [
                sshPublisherDesc(
                configName: "docker-host",
                verbose: true,
                transfers: [
                sshTransfer(
                    sourceFiles: ".",
                    removePrefix: "",
                    remoteDirectory: "php_nginx/src",
                    execCommand: ""
                )
                ])
            ])
            }
        }
    }
}