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
                echo "Fetching the source code from the directory path: $DIRECTORY_PATH"
                echo "Compiling the code and generating necessary artifacts"
            }
        }
        
        stage("Test")
        {
            steps
            {
                echo "Running unit tests"
                echo "Running integration tests"
            }
        }
        
        
        stage("Code Quality Check")
        {
            steps
            {
                echo "Checking the quality of the code"
            }
        }

        stage("Deploy")
        {
            steps
            {
                echo "Deploying the application to the testing environment: $TESTING_ENVIRONMENT"  
            }
        }
        
        stage("Approval")
        {
            steps
            {
                sleep 10
            }
        }

        stage("Deploy to Production")
        {
            steps
            {
                echo "Deploying the code to the production environment: $PRODUCTION_ENVIRONMENT" 
            }
        }
    }
}
