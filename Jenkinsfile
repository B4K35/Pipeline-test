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
                post 
                {
                    success 
                    {
                        mail to: 's222292111@deakin.edu.au',
                        subject: 'Success - Build Status',
                        body: "Build has successfully been completed."
                        
                    }
                    failure 
                    {
                        mail to: 's222292111@deakin.edu.au',
                        subject: 'Failed - Build Status',
                        body: "Build failed."
                    }
                }
            }
        }
        
        stage("Unit and Integration Tests")
        {
            steps
            {
                // - Run unit tests to ensure the code functions as expected and run integration tests to ensure the different components of the application work together as expected.
                echo 'Running the unit and integration tests using Selenium and JUnit'
                post 
                {
                    success 
                    {
                        mail to: 's222292111@deakin.edu.au',
                        subject: 'Success - Unit and Integration Tests',
                        body: "Unit and Integration Tests have successfully been completed."
                        
                    }
                    failure 
                    {
                        mail to: 's222292111@deakin.edu.au',
                        subject: 'Failed - Unit and Integration Tests',
                        body: "Unit and Integration Tests failed."
                    }
                }
            }
        }
        
        
        stage("Code Analysis")
        {
            steps
            {
                // - Integrate a code analysis tool to analyse the code and ensure it meets industry standards.
                echo 'Analyzing the code using Jenkins and SonarQube'
                post 
                {
                    success 
                    {
                        mail to: 's222292111@deakin.edu.au',
                        subject: 'Success - Unit and Integration Tests',
                        body: "Code Analysis successfully completed."
                        
                    }
                    failure 
                    {
                        mail to: 's222292111@deakin.edu.au',
                        subject: 'Failed - Unit and Integration Tests',
                        body: "Code Analysis failed."
                    }
                }
            }
        }

        stage("Security Scan")
        {
            steps
            {
                // - Perform a security scan of the code using a tool to identify any vulnerabilities.
                echo 'Performing a security scan on the code using OWASP ZAP'
                post 
                {
                    success 
                    {
                        mail to: 's222292111@deakin.edu.au',
                        subject: 'Success - Security Scan',
                        body: "Security Scan successfully completed."
                        
                    }
                    failure 
                    {
                        mail to: 's222292111@deakin.edu.au',
                        subject: 'Failed - Security Scan',
                        body: "Security Scan failed."
                    }
                }
            }
        }
        
        stage("Deploy to Staging")
        {
            steps
            {
                echo 'Deploying the application to an AWS EC2 instance'
                post 
                {
                    success 
                    {
                        mail to: 's222292111@deakin.edu.au',
                        subject: 'Success - Unit and Integration Tests',
                        body: "Deploy to Staging successfully completed."
                        
                    }
                    failure 
                    {
                        mail to: 's222292111@deakin.edu.au',
                        subject: 'Failed - Unit and Integration Tests',
                        body: "Deploy to Staging failed."
                    }
                }
            }
        }

        stage("Integration Tests on Staging")
        {
            steps
            {
                echo 'Running integration tests on the staging environment using Selenium'
                post 
                {
                    success 
                    {
                        mail to: 's222292111@deakin.edu.au',
                        subject: 'Success - Integration Tests on Staging',
                        body: "Integration Tests on Staging has successfully been completed."
                        
                    }
                    failure 
                    {
                        mail to: 's222292111@deakin.edu.au',
                        subject: 'Failed - Integration Tests on Staging',
                        body: "Integration Tests on Staging failed."
                    }
                }           
            }
        }

        stage("Deploy to Production")
        {
            steps
            {
                echo 'Deploying the application to an AWS EC2 instance'
                post 
                {
                    success 
                    {
                        mail to: 's222292111@deakin.edu.au',
                        subject: 'Success - Deploy to Production',
                        body: "Deploy to Production was successfully been completed."
                        
                    }
                    failure 
                    {
                        mail to: 's222292111@deakin.edu.au',
                        subject: 'Failed - Deploy to Production',
                        body: "Deploy to Production failed."
                    }
                }
            }
        }
    }
}
