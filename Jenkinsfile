node('ubuntu-APPserver')
{

def app 
stage('Cloning git')
{
    /*code for cloning repository to our workspace */
    checkout scm
}

stage('Build-and-tag')
{
    /*this builds the image
        this is synonymous to docker build on the CLI */
    app = docker.build('zimmate2/car_web_new')
}

stage('Push-to-docker')
{
    /* this code pushes the changes to docker hub*/
    docker.withRegistry('https://registry.hub.docker.com')
}

stage('Push-to-docker')
{
    /* this code pushes the changes to docker hub*/
    docker.withRegistry('https://registry.hub.docker.com', 'zimmate')
}

stage('Deploy')
{
    sh "docker-compose down"
    sh "docker-compose up -d"
}

}
