## 目的
maven-repo仓库的各个模块为开发者提供了最基本的操作以便敏捷开发。
## 操作手册位置
* [https://github.com/BonaparteDawn/maven-repo/wiki](https://github.com/BonaparteDawn/maven-repo/wiki)
## 例子
例子：pom.xml文件中引用通用模块依赖
```javascript
<dependencies>
    <dependency><!--通用模块-->
        <groupId>github.bonapartedawn</groupId>
        <artifactId>common</artifactId>
        <version>1.0.1-RELEASE</version>
    </dependency>
</dependencies>
<!--仓库地址-->
<repositories>
    <repository>
        <id>github.bonapartedawn</id>
        <url>
	      https://raw.githubusercontent.com/BonaparteDawn/maven-repo/master/releases
	</url>
    </repository>
</repositories>
```
例子：pom.xml文件中引用mybatis-plugin插件
```javascript
<!--插件仓库地址-->
<dependencies>
<dependency>
    <groupId>org.mybatis</groupId>
    <artifactId>mybatis</artifactId>
    <version>3.4.1</version>
</dependency>
</dependencies>
<pluginRepositories>
<pluginRepository>
    <id>github.bonapartedawn</id>
    <url>https://raw.githubusercontent.com/BonaparteDawn/maven-repo/master/releases</url>
</pluginRepository>
</pluginRepositories>
<build>
<plugins>
    <plugin>
	<groupId>org.mybatis.generator</groupId>
	<artifactId>mybatis-generator-maven-plugin</artifactId>
	<version>1.3.2</version>
	<configuration>
	    <verbose>true</verbose>
	    <overwrite>true</overwrite>
	</configuration>
	<dependencies>
	    <dependency>
		<groupId>mysql</groupId>
		<artifactId>mysql-connector-java</artifactId>
		<version>5.1.6</version>
	    </dependency>
	    <dependency>
		<groupId>org.mybatis.generator</groupId>
		<artifactId>mybatis-generator-core</artifactId>
		<version>1.3.5</version>
	    </dependency>
	    <dependency>
		<groupId>org.mybatis</groupId>
		<artifactId>mybatis</artifactId>
		<version>3.4.1</version>
	    </dependency>
	    <dependency>
		<groupId>github.bonapartedawn</groupId>
		<artifactId>mybatis-plugin</artifactId>
		<version>1.0-RELEASE</version>
	    </dependency>
	</dependencies>
    </plugin>
    <plugin>
	<groupId>github.bonapartedawn</groupId>
	<artifactId>mybatis-plugin</artifactId>
	<version>1.0-RELEASE</version>
	<executions>
	    <execution>
		<goals>
		    <goal>MyBatisClean</goal>
		</goals>
	    </execution>
	</executions>
	<configuration>
	    <path>generatorConfig.xml</path>
	</configuration>
    </plugin>
</plugins>
</build>
```
## 有问题反馈
在使用中有任何问题，欢迎反馈给我，可以用以下联系方式跟我交流
* 邮件：bonapartedawn@163.com
*  QQ: 952851112
