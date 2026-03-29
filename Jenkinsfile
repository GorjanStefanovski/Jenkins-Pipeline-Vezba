node {
  def app 
  
  stage('Clone repository') {
        checkout scm
  }
  
  stage('Build image') {
        app = docker.build("gorjanstefanovski/kiii-jenkins")
  }
  
  stage('Push image') {
        docker.withRegistry('https://registry.hub.docker.com', 'vezbaid') {
            app.push('latest')
        }
  }
}
