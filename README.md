# Step to execute the API test in Jenkins
1. Import the Swagger json file to your postman
2. Add JS assertion in "Test" tab in postman
3. Install Newman
4. Install Jenkins
5. Create new Item in Jenkins
6. Choose the pipeline
7. In Configure you can fill script for example :
   pipeline {
    agent any
    
    stages {
        stage('Install Newman') {
            steps {
                // Install newman dengan sudo
                sh '''
                sudo npm install -g newman
                newman --version
                '''
            }
        }
        
        stage('Run Tests') {
            steps {
                sh 'newman run ./Users/ahadev1/Documents/Task.json -e ./Users/ahadev1/Documents/Task.json'
            }
        }
    }
}
9. And then apply and save
10. Build Now
