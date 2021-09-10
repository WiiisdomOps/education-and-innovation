node {
    // Path to the Kinesis CLI executable on the Jenkins server.
    // Kinesis CLI executable needs to be installed on the Jenkins server to run Kinesis tests.
    // Change it to fit to your installation.
    def kinesis = "/var/jenkins_home/bin/kinesis-cli/kinesis"

    // For security reasons the context variables are masked in this GitHub project.
    // It is possible to keep it in your private repository but the recommended way to store
    // this files separately on the on the Jenkins server
    def context = "/var/jenkins_home/kinesis-context/jenkins_tableau_10.2.json"

    currentBuild.result = "SUCCESS"

    try {
        stage('Checkout') {
            echo("Checkout")
            checkout scm
        }

        stage('Cleanup') {
            echo("Cleanup")
            sh('rm -f kinesis.log')
            sh('find . -depth -type d -name "report-*" -exec rm -r "{}" \\;')
        }

        stage('Kinesis Tableau Test') {
            echo("Kinesis Tableau Test")
            def pwd = pwd()
            def kinesisTimeout = 75

            // Run Kinesis CLI as a shell command
            // Every parameters is escaped to avoid issues with whitespace characters
            sh("\"${kinesis}\" --path \"${pwd}\" --context-vars \"${context}\" --canvas-timeout \"${kinesisTimeout}\" --output \"${pwd}\" --recursive")
        }

    } catch (e) {
        currentBuild.result = "FAILED"
        throw e;
    } finally {
        stage('Archive Test Reports') {
            archiveArtifacts artifacts: '**/report-*/'
        }
    }
}
