 ASPECTJ TUTORIAL
-------------------
#### Getting Start
### Using maven
1. Getting maven
```
mkdir ~/maven
cd ~/maven
curl -O \
  http://mirrors.advancedhosters.com/apache/maven/maven-3/3.3.9/binaries/apache-maven-3.3.9-bin.tar.gz
tar xvfz apache-maven-3.3.9-bin.tar.gz
export MAVEN_HOME=$(pwd)/apache-maven-3.3.9
```
2. Generate maven project
```
mvn archetype:generate -DgroupId=edu.tutorial.aspectj -DartifactId=aspectj_quick_start \        
  -DarchetypeGroupId=org.apache.maven.archetypes \
  -DarchetypeArtifactId=maven-archetype-quickstart   -DarchetypeVersion=RELEASE
```
Maven aspectj Plugin:
```
<plugin>
	<groupId>org.codehaus.mojo</groupId>
	<artifactId>aspectj-maven-plugin</artifactId>
	<version>1.8</version>
	<dependencies>
		<dependency>
			<groupId>org.aspectj</groupId>
			<artifactId>aspectjrt</artifactId>
						<version>1.8.7</version>
					</dependency>
					<dependency>
						<groupId>org.aspectj</groupId>
						<artifactId>aspectjtools</artifactId>
						<version>1.8.7</version>
					</dependency>

					<dependency>
						<groupId>org.aspectj</groupId>
						<artifactId>aspectjweaver</artifactId>
						<version>1.8.7</version>
					</dependency>
				</dependencies>
				
				<configuration>
					<source>1.8</source>
					<target>1.8</target>
					<complianceLevel>1.8</complianceLevel>
					<showWeaveInfo>true</showWeaveInfo>
    				<aspectDirectory>src/</aspectDirectory>

				</configuration>
				<executions>
					<execution>
						<phase>process-sources</phase>
						<goals>
							<goal>compile</goal>       <!-- use this goal to weave all your main classes -->
							<goal>test-compile</goal>  <!-- use this goal to weave all your test classes -->
				</goals>
			</execution>
		</executions>
</plugin>
```
