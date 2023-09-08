pipeline {
    agent any
    environment
    {
        DIRECTORY_PATH = "C:\\ProgramData\\Jenkins\\projects\\production"
        TESTING_ENVIRONMENT = "C:\\ProgramData\\Jenkins\\projects\\test"
        PRODUCTION_ENVIRONMENT = "Drew's Production Enviroment"
    }

    stages
    {
        stage("Build")
        {
            steps
            {
                // - Build the code using a build automation tool to compile and package your code. 
                echo "Fetching the source code from the directory path: $DIRECTORY_PATH"
                echo "Compiling the code and generating necessary artifacts."
                sh 'mvn clean install'
            }
        }
        
        stage("Unit and Integration Tests")
        {
            steps
            {
                // - Run unit tests to ensure the code functions as expected and run integration tests to ensure the different components of the application work together as expected.
                echo "Running unit tests"
                echo "Running integration tests."
                sh 'mvn test'
            }
        }
        
        
        stage("Code Analysis")
        {
            steps
            {
                // - Integrate a code analysis tool to analyse the code and ensure it meets industry standards.
                echo "Checking the quality of the code."
                sh 'sonar-scanner'
            }
        }

        stage("Security Scan")
        {
            steps
            {
                // - Perform a security scan of the code using a tool to identify any vulnerabilities.
                sh 'owasp-dependency-check.sh'
            }
        }
        
        stage("Deploy to Staging")
        {
            steps
            {
                sh 'ssh ec2-user@staging-server "mkdir -p /var/www/app"'
                sh 'scp -r target/app.war ec2-user@staging-server:/var/www/app'
            }
        }

        stage("Integration Tests on Staging")
        {
            steps
            {
                sh 'ssh ec2-user@staging-server "curl -s http://localhost:8080/"'            
            }
        }

        stage("Deploy to Production")
        {
            steps
            {
                sh 'ssh ec2-user@production-server "mkdir -p /var/www/app"'
                sh 'scp -r target/app.war ec2-user@production-server:/var/www/app'
            }
        }
    }
}
