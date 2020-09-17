# spring boot
  1. 
  Create new spring boot project
  
  2. 
  a <build>
  a    <plugins>
  a        <plugin>
  a            <groupId>org.springframework.boot</groupId>
  a            <artifactId>spring-boot-maven-plugin</artifactId>
  a        </plugin>
  a        <plugin>
  a            <groupId>com.github.eirslett</groupId>
  a            <artifactId>frontend-maven-plugin</artifactId>
  a            <version>1.6</version>
  a            <configuration>
  a                <nodeVersion>v9.11.2</nodeVersion>
  a            </configuration>
  a            <executions>
  a                <execution>
  a                    <id>install-npm</id>
  a                    <goals>
  a                        <goal>install-node-and-npm</goal>
  a                    </goals>
  a                </execution>
  a            </executions>
  a        </plugin>
  a    </plugins>
  a  </build>
    
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

