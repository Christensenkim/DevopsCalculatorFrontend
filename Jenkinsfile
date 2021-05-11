pipeline {
    agent any
    stages {
        stage ("Build"){
            steps {
                parallel(
                    web: {
                        dir("web") {
                            echo "===== OPTIONAL: Will build the website (if needed) ====="
                        }
                    }
                    api: {
                        dir("api") {
                            echo "===== REQUIRED: Will build the API project ====="
                        }
                    }
                    db: {
                        dir("db") {
                            echo "===== OPTIONAL: Will build the database (if using a state-based approach) ====="
                        }
                    }
                )
            }
        }

        stage("Test API") {
            steps {
                echo "===== REQUIRED: Will execute unit tests of the API project ====="
            }
        }
        stage("Deliver Web") {
            steps {
                echo "===== REQUIRED: Will deliver the website to Docker Hub ====="
            }
        }
        stage("Deliver API") {
            steps {
                echo "===== REQUIRED: Will deliver the API to Docker Hub ====="
            }
        }
        stage("Release staging environment") {
            steps {
                echo "===== REQUIRED: Will use Docker Compose to spin up a test environment ====="
            }
        }
        stage("Automated acceptance test") {
            steps {
                echo "===== REQUIRED: Will use Selenium to execute automatic acceptance tests ====="
            }
        }
    }
}