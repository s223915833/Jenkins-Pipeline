pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                echo "Building..."
            }
            post{
                success{
                    mail to: "ns.kehelpannala@gmail.com",
                    subject: "Build status Email",
                    body: "Build was successful!"
                }
            }
        }
    }
}