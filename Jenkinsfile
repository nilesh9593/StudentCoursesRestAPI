node("docker") {  
   
    stage('Build') { 
       //git build
       git 'https://github.com/nilesh9593/StudentCoursesRestAPI.git'
    }
    stage('docker') {
        sh 'docker image build . -t nileshhabib16794/studentcourserestservice:1.0' 
    }
    stage('push'){
        withDockerRegistry(credentialsId: 'dockerhub', url: 'https://index.docker.io/v1/') {
            image= docker.build ("nileshhabib16794/studentcourserestservice:1.0")
            image.push()
        }
    }
    stage('container'){
        sh 'docker container run -P -d nileshhabib16794/studentcourserestservice:1.0'
    }
}
