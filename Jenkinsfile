pipeline{
    agent{
        Docker{
            image 'node6-alpine'
        }
    }
    enviroment{
        CI = 'true'
    }
    stages{
        stage('Build'){
            steps{
                sh 'npm install'
                sh 'npm run build'
            }
        }
        stage('Deliver'){
            steps{
                sh 'npm install netlify-cli'
                sh 'npx netlify deploy --site $NETLIFY_SITE_ID --auth $NETLIFY_AUTH_TOKEN --dir build/ --prod'
            }
        }

    }
}