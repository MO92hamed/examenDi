# Spring Boot application

This is an simple backend using Java / Maven / Spring boot with postgresql database  for an book application that can be used to add, delete and update books .

## Dependencies

  - Java
  - Maven
  - Postgresql
  - spring boot
  

## Configure the project

  we use spring initializr to configure our application , maven project java 17 as language spring boot version (3.0.2), 
  and configure project metadata then choose packaging Jar.
  And finally we add  necessary dependencies :
      * Spring web
      * Spring Boot DevTools
      * lambok
      * PostgreSQLDriver
      * Spring Data JPA
      * Validation
      ### In pom.xml:
      
          <dependencies>
              <dependency>
                  <groupId>org.springframework.boot</groupId>
                  <artifactId>spring-boot-starter-data-jpa</artifactId>
              </dependency>
              <dependency>
                  <groupId>org.springframework.boot</groupId>
                  <artifactId>spring-boot-starter-web</artifactId>
              </dependency>
              <dependency>
                  <groupId>org.springframework.boot</groupId>
                  <artifactId>spring-boot-starter-validation</artifactId>
                  <version>3.0.2</version>
              </dependency>
              <dependency>
                  <groupId>org.springframework.boot</groupId>
                  <artifactId>spring-boot-devtools</artifactId>
                  <scope>runtime</scope>
                  <optional>true</optional>
              </dependency>
              <dependency>
                  <groupId>org.postgresql</groupId>
                  <artifactId>postgresql</artifactId>
                  <scope>runtime</scope>
              </dependency>
              <dependency>
                  <groupId>org.projectlombok</groupId>
                  <artifactId>lombok</artifactId>
                  <optional>true</optional>
              </dependency>
              <dependency>
                  <groupId>org.springframework.boot</groupId>
                  <artifactId>spring-boot-starter-test</artifactId>
                  <scope>test</scope>
              </dependency>
         </dependencies>
      
 ## About Service
 
   The service is just a simple Book review REST service. It uses an relational database (PostgreSQL) to store the data.
   If your database connection properties work, you can call some REST endpoints defined in com.examenspring.examendi.controller.LivreController on port 8080.
   
   Here are some endpoints you can call:
   
      | M??thodes          |     URLs                    |         Actions |
      |-------------------|-----------------------------|-----------------|
      |     POST          |       /api/livres           | 	create a new book
      |     GET           |	      /api/livres           |	  collect all the books
      |     GET           |       /api/livres/:id       |	  retrieve a book by :id
      |     PUT           |	      /api/livres/:id       |	  update a book by :id
      |     DELETE        | 	    /api/livres/:id       |	  delete a book by :id
      |     DELETE        |	      /api/livres           |	  delete all books
      |     GET 	        | /api/livres?titre=[mot-cl??] |	  find all books that contain the title
      
      
 ## Running the project with POSTGRESQL
 
   Here is what you would do to back the services with POSTGRESQL, for example:
   
   ### In pom.xml add:
    
        <dependency>
            <groupId>org.postgresql</groupId>
            <artifactId>postgresql</artifactId>
            <scope>runtime</scope>
        </dependency>
        
   ### Append this to the end of application.yml: 
   
      spring:
        datasource:
           url: jdbc:postgresql://<your_postgresql_host_or_ip>/bootexample
           username: <your_postgresql_username>
           password: <your_postgresql_password>
           driver-class-name: org.postgresql.Driver
        jpa:
          show-sql: true
          hibernate:
             ddl-auto: create-drop
          properties:
             hibernate:
                format_sql: true
          database: postgresql
          database-platform: org.hibernate.dialect.PostgreSQLDialect
 
      
  
  
  
  
