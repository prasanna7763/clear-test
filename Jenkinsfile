node("host") {
        stage("remove old containers"){
          //sh "sudo docker rm -f v1.1-green1 v1.1-green2 sboot_demo_pg ng"      
        }
        stage("Start containers - Blue"){   
          sh "sudo docker run -d --env=POSTGRES_PASSWORD=demo_pass  -p 5432:5432  --name sboot_demo_pg devopsevd/sboot_demo_pg"
          sh "sudo docker run -d --name v1.0-blue1 -p 8180:8180 -e app.version='v1.0-blue-node1'  --link sboot_demo_pg:sboot_demo_pg devopsevd/sboot:v1.0-blue"
          sh "'sudo docker run -d --name v1.0-blue2 -p 8280:8180 -e app.version='v1.0-blue-node2'  --link sboot_demo_pg:sboot_demo_pg devopsevd/sboot:v1.0-blue"
          sh "sudo docker run -P -d --name ng -p 80:80 devopsevd/nginx_img"
        }       
       
}
