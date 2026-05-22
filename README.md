#SOAP

<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">

    <modelVersion>4.0.0</modelVersion>

    <groupId>com.mycompany</groupId>
    <artifactId>test_wdls</artifactId>
    <version>1.0-SNAPSHOT</version>
    <packaging>jar</packaging>

    <properties>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
        <maven.compiler.release>21</maven.compiler.release>
    </properties>

    <dependencies>

        <dependency>
            <groupId>com.sun.xml.ws</groupId>
            <artifactId>jaxws-rt</artifactId>
            <version>4.0.2</version>
        </dependency>

    </dependencies>

    <build>
        <plugins>

            <plugin>
                <groupId>com.sun.xml.ws</groupId>
                <artifactId>jaxws-maven-plugin</artifactId>
                <version>4.0.2</version>

                <executions>

                    <!-- DataService -->
                    <execution>
                        <id>wsimport-generate-DataService</id>

                        <phase>generate-sources</phase>

                        <goals>
                            <goal>wsimport</goal>
                        </goals>

                        <configuration>

                            <wsdlUrls>
                                <wsdlUrl>
                                    http://36.50.135.242:2221/DataService?wsdl
                                </wsdlUrl>
                            </wsdlUrls>

                            <packageName>
                                com.mycompany.dataservice
                            </packageName>

                            <sourceDestDir>
                                ${project.build.directory}/generated-sources/wsimport
                            </sourceDestDir>

                            <keep>true</keep>
                            <verbose>true</verbose>
                            <extension>true</extension>

                        </configuration>
                    </execution>

                    <!-- CharacterService -->
                    <execution>
                        <id>wsimport-generate-CharacterService</id>

                        <phase>generate-sources</phase>

                        <goals>
                            <goal>wsimport</goal>
                        </goals>

                        <configuration>

                            <wsdlUrls>
                                <wsdlUrl>
                                    http://36.50.135.242:2221/CharacterService?wsdl
                                </wsdlUrl>
                            </wsdlUrls>

                            <packageName>
                                com.mycompany.characterservice
                            </packageName>

                            <sourceDestDir>
                                ${project.build.directory}/generated-sources/wsimport
                            </sourceDestDir>

                            <keep>true</keep>
                            <verbose>true</verbose>
                            <extension>true</extension>

                        </configuration>
                    </execution>

                    <!-- ObjectService -->
                    <execution>
                        <id>wsimport-generate-ObjectService</id>

                        <phase>generate-sources</phase>

                        <goals>
                            <goal>wsimport</goal>
                        </goals>

                        <configuration>

                            <wsdlUrls>
                                <wsdlUrl>
                                    http://36.50.135.242:2221/ObjectService?wsdl
                                </wsdlUrl>
                            </wsdlUrls>

                            <packageName>
                                com.mycompany.objectservice
                            </packageName>

                            <sourceDestDir>
                                ${project.build.directory}/generated-sources/wsimport
                            </sourceDestDir>

                            <keep>true</keep>
                            <verbose>true</verbose>
                            <extension>true</extension>

                        </configuration>
                    </execution>

                </executions>

            </plugin>

            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>3.13.0</version>

                <configuration>
                    <release>21</release>
                </configuration>

            </plugin>

        </plugins>
    </build>

</project>
