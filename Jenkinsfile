pipeline {
    agent any
    stages {
        stage('One') {
            steps {
                echo "Hi, This is jashim from Edureka"
            }
        }
        stage('Two') {
            steps {
                input("Do you want to proceed ?")
            }
        }
        stage('Three') {
            steps {
                when {
                    not {
                        branch "master"
                    }
                }
                steps {
                    echo "hello"
                }
                
            }
        }
        
        stage('Four') {
            parallel {
                    stage('Unit Test') {
                            steps {
                                echo "Running the unit Test"
                            }
                    }    
                    stage('Integration Test') {
                            agent {
                               
                                    docker {
                                            reuseNode false
                                            image 'ubuntu'
                                    }        
                            }        
                            steps {
                                echo "Running..... the Integration Test"
                            }
                    }    
            
            }
        }
        
        
        
    }
}
