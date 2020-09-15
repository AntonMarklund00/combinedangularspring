# spring boot
  1. 
  Create new spring boot project
  
  2. 
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
                  <nodeVersion>v9.11.2</nodeVersion>
              </configuration>
              <executions>
                  <execution>
                      <id>install-npm</id>
                      <goals>
                          <goal>install-node-and-npm</goal>
                      </goals>
                  </execution>
              </executions>
          </plugin>
      </plugins>
    </build>
    
  3. 
  maven generate-source

# Angular
  1. ng new XXXX
  
  2.  
  cat XXXX/.gitignore >> .gitignore
  rm -rf XXXX/node* XXXX/src/favicon.ico XXXX/.gitignore XXXX/.git
  sed -i -e 's/node_/anode/' .gitignore
  cp -rf XXXX/* .
  cp XXXX/.??* .
  rm -rf XXXX
  sed -i -e 's,dist/XXXX,target/classes/static,' XXXX
  
# spring boot
  1.
  <execution>
      <id>npm-install</id>
      <goals>
          <goal>npm</goal>
      </goals>
   </execution>

  2. 
  maven generate-source
  
  3. 
  <execution>
        <id>npm-build</id>
        <goals>
            <goal>npm</goal>
        </goals>
        <configuration>
            <arguments>run-script build</arguments>
        </configuration>
      </execution>
      
  4. 
  maven generate-source
  
  5. 
  ng build --watch

