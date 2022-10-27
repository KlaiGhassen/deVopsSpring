pipeline{
    agent any

    stages{


        stage('Cloning from GitHub') {
                steps {
                    git branch: 'main', url: 'https://github.com/KlaiGhassen/deVopsSpring'
                }
                
            }
      
      stage('Clean maven'){
            steps {
                sh 'mvn clean '
            }
            
        }
        stage('Compile project'){
            steps {
                sh 'mvn compile  -DskipTests'
            }
            
        }
        
        
        /* stage('UNIT test'){
            steps{
                sh 'mvn test'
            }
        }*/

         stage('SonarQube Analysis'){
                steps {
                    sh """mvn sonar:hinda2100@@ -DskipTests \
                            -Dsonar.language=java \
                          
                            
                    """
                }
                
            }
        
        
        
        
        stage('Nexus'){
            steps{
                sh 'mvn deploy -DskipTests'
            }
        }
        
        
      

    }
}
