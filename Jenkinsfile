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
                echo 'Building the code using Maven'
            }
            post 
            {
                success 
                {
                    to: 's222292111@deakin.edu.au',
                    attachLog: true,
                    subject: 'Success - Build Status',
                    body: "Build has successfully been completed." 
                    
                    
                }
                failure 
                {
                    to: 's222292111@deakin.edu.au',
                    attachLog: true,
                    subject: 'Failed - Build Status',
                    body: "Build failed."
                }
            }
        }
        
        stage("Unit and Integration Tests")
        {
            steps
            {
                // - Run unit tests to ensure the code functions as expected and run integration tests to ensure the different components of the application work together as expected.
                echo 'Running the unit and integration tests using Selenium and JUnit'
            }
            post 
            {
                success 
                {
                    to: 's222292111@deakin.edu.au',
                    attachLog: true,
                    subject: 'Success - Unit and Integration Tests',
                    body: "Unit and Integration Tests have successfully been completed."                     
                }
                failure 
                {
                    to: 's222292111@deakin.edu.au',
                    attachLog: true,
                    subject: 'Failed - Unit and Integration Tests',
                    body: "Unit and Integration Tests failed." 
                }
            }
        }
        
        
        stage("Code Analysis")
        {
            steps
            {
                // - Integrate a code analysis tool to analyse the code and ensure it meets industry standards.
                echo 'Analyzing the code using Jenkins and SonarQube'
            }
            post 
            {
                success 
                {
                    emailext to: 's222292111@deakin.edu.au',
                    attachLog: true,
                    subject: 'Success - Code Analysis',
                    body: "Code Analysis successfully completed." 
                }
                failure 
                {
                    emailext to: 's222292111@deakin.edu.au',
                    attachLog: true,
                    subject: 'Failed - Code Analysis',
                    body: "Code Analysis failed." 
                }
            }
        }

        stage("Security Scan")
        {
            steps
            {
                // - Perform a security scan of the code using a tool to identify any vulnerabilities.
                echo 'Performing a security scan on the code using OWASP ZAP'
            }
            post 
            {
                success 
                {
                    emailext to: 's222292111@deakin.edu.au',
                    attachLog: true,
                    subject: 'Success - Security Scan',
                    body: "Security Scan successfully completed."
                }
                failure 
                {
                    emailext to: 's222292111@deakin.edu.au',
                    attachLog: true,
                    subject: 'Failed - Security Scan',
                    body: "Security Scan failed." 
                }
            }
        }
        
        stage("Deploy to Staging")
        {
            steps
            {
                // - Deploy the application to a staging server (e.g., AWS EC2 instance).
                echo 'Deploying the application to an AWS EC2 instance'
            }
            post 
            {
                success 
                {
                    emailext to: 's222292111@deakin.edu.au',
                    attachLog: true,
                    subject: 'Success - Deploy to Staging',
                    body: "Deploy to Staging successfully completed." 
                }
                failure 
                {
                    emailext to: 's222292111@deakin.edu.au',
                    attachLog: true,
                    subject: 'Failed - Deploy to Staging',
                    body: "Deploy to Staging failed." 
                }
            }
        }

        stage("Integration Tests on Staging")
        {
            steps
            {
                // - Run integration tests on the staging environment to ensure the application functions as expected in a production-like environment.
                echo 'Running integration tests on the staging environment using Selenium'
            }
            post 
            {
                success 
                {
                    emailext to: 's222292111@deakin.edu.au',
                    attachLog: true,
                    subject: 'Success - Integration Tests on Staging',
                    body: "Integration Tests on Staging has successfully been completed." 
                } 
                failure 
                {
                    emailext to: 's222292111@deakin.edu.au',
                    attachLog: true,
                    subject: 'Failed - Integration Tests on Staging',
                    body: "Integration Tests on Staging failed." 
                }           
            }
        }

        stage("Deploy to Production")
        {
            steps
            {
                // - Deploy the application to a production server (e.g., AWS EC2 instance).
                echo 'Deploying the application to an AWS EC2 instance'
            }
            post 
            {
                success 
                {
                    emailext to: 's222292111@deakin.edu.au',
                    attachLog: true,
                    subject: 'Success - Deploy to Production',
                    body: "Deploy to Production was successfully been completed." 
                }
                failure 
                {
                    emailext to: 's222292111@deakin.edu.au',
                    attachLog: true,
                    subject: 'Failed - Deploy to Production',
                    body: "Deploy to Production failed."
                }
            }
        }
    }
}
