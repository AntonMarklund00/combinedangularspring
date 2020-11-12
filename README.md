# step by step how to use frontend-maven-plugin to develop projects with spring boot and angular in only one file

### 1. 

  Create new spring boot project
  (I recommend to add DevTools as a dependency) 
 
### 2. 
  Change your build in .POM to: 
  ```xml
   <build>
    <plugins>
      <plugin>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-maven-plugin</artifactId>
      </plugin>
      <plugin>
        <groupId>com.github.eirslett</groupId>
        <artifactId>frontend-maven-plugin</artifactId>
        <version>1.6</version>
        <configuration>
          <nodeVersion>v12.0.0</nodeVersion>
        </configuration>
        <executions>
          <execution>
            <id>install-npm</id>
            <goals>
              <goal>install-node-and-npm</goal>
            </goals>
          </execution>
          <execution>
            <id>npm-install</id>
            <goals>
              <goal>npm</goal>
            </goals>
          </execution>
          <execution>
            <id>npm-build</id>
            <goals>
              <goal>npm</goal>
            </goals>
            <configuration>
              <arguments>run-script build</arguments>
            </configuration>
          </execution>
        </executions>
      </plugin>
    </plugins>
  </build>
   ```
### 3.     
  Once you have made this change do: 
  maven generate-source

## Angular
### 1. 
  ```
  cd your-spring-project
  ng new your-angular-name
  ```
  
### 2.
```cmd
  cat your-angular-project/.gitignore >> .gitignore
  rm -rf your-angular-project/node* your-angular-project/src/favicon.ico your-angular-project/.gitignore your-angular-project/.git
  sed -i -e 's/node_/anode/' .gitignore
  cp -rf your-angular-project/* .
  cp your-angular-project/.??* .
  rm -rf your-angular-project
  sed -i -e 's,dist/your-angular-project,target/classes/static,' angular.json
  ```
  
### 3. 
  ```cmd
  cd your-spring-project
  ng build --watch
  ```

#### Now if you start your Spring boot application you should be able see your angular application on localhost:8080 (provided you use this port). And be able to make live changes in the angular project.
