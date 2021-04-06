node("TestServer") {
        stage("remove old containers"){
          sh  "sudo docker ps -a -q --filter=ancestor=10.240.0.10:8123/springboot:v0.1 | xargs -r sudo docker rm -f"      
        }       
}
