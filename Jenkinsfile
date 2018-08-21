node("AppServer") {
        stage("remove old containers"){
          sh "docker ps -a -q --filter=ancestor=devopsevd/nginx_img --filter=ancestor=10.144.2.110:8123/sboot:v1.1-green --filter=ancestor=devopsevd/sboot:v1.1-green --filter=ancestor=devopsevd/sboot:v1.0-blue --filter=ancestor=devopsevd/sboot_demo_pg | xargs -r docker rm -f"      
        }       
}
