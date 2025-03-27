This url is used to get default file : -> http://192.168.1.117:8085/application/default


steps : 
1. create new service for confing server
2. Add dependency for config server and eureka client
3. enable @Descoveryclient and @EnableconfigServer annotation
4. Add some configuration in config server --->server like :
5. 
  server:
    port:  8085
  spring:
    application:
      name: CONFIG-SERVER
  
    cloud:
      config:
        server:
          git:
            uri:  https://github.com/Radhika-yaduvanshi/configuration-service.git
            clone-on-start: true

5.Add you common configuration in your github config-server.yml file

6.Add dependency for client  in another services 

7.Add configuration -->

    spring:
      config:
        import: optional:configserver:http://localhost:8085

   
