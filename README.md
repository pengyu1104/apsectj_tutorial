 ASPECTJ TUTORIAL
-------------------
Maven aspectj Plugin:
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
