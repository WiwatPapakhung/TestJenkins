# USSD000 Gateway Framework

## Environment for development
* JDK 8 
* Maven 3.5.0
* Spring Boot 1.5.3.RELEASE

### Intro
USSD000 project has created for example USSD Gateway framework to calling 3rd Party service as below
* Salt service
* Sdp service
* CBS-UVC Service

### How to running this project
* Build and Package jar files

```
	$> mvn package -Dmaven.test.skip=true
	[INFO] Scanning for projects...
	[INFO]
	[INFO] ------------------------------------------------------------------------
	[INFO] Building ussd000 0.1.0
	[INFO] ------------------------------------------------------------------------
	[INFO]
	[INFO] --- maven-resources-plugin:2.6:resources (default-resources) @ ussd000 ---
	[INFO] Using 'UTF-8' encoding to copy filtered resources.
	[INFO] Copying 5 resources
	[INFO] Copying 9 resources
	[INFO]
	[INFO] --- maven-compiler-plugin:3.1:compile (default-compile) @ ussd000 ---
	[INFO] Nothing to compile - all classes are up to date
	[INFO]
	[INFO] --- maven-resources-plugin:2.6:testResources (default-testResources) @ ussd000 ---
	[INFO] Not copying test resources
	[INFO]
	[INFO] --- maven-compiler-plugin:3.1:testCompile (default-testCompile) @ ussd000 ---
	[INFO] Not compiling test sources
	[INFO]
	[INFO] --- maven-surefire-plugin:2.18.1:test (default-test) @ ussd000 ---
	[INFO] Tests are skipped.
	[INFO]
	[INFO] --- maven-jar-plugin:2.6:jar (default-jar) @ ussd000 ---
	[INFO] Building jar: /Volumes/Macintosh_Data/Data/dtacGitWorkspace/spring-boot-workspace/poc-workspace/ussd000/target/ussd000.jar
	[INFO]
	[INFO] --- spring-boot-maven-plugin:1.5.3.RELEASE:repackage (default) @ ussd000 ---
	[INFO] ------------------------------------------------------------------------
	[INFO] BUILD SUCCESS
	[INFO] ------------------------------------------------------------------------
	[INFO] Total time: 2.671 s
	[INFO] Finished at: 2017-08-10T20:49:16+07:00
	[INFO] Final Memory: 22M/314M
	[INFO] ------------------------------------------------------------------------
	[WARNING] The requested profile "artifactory" could not be activated because it does not exist.
```
* (Optional) Modify shell script "runapps.ksh" to setting postfix configuration (dev/test/prod) or update System properties as below

```
	#!/bin/ksh
	
	typeset JAVA_OPTS="-Dserver.name=ijetm1 -Dspring.profiles.active=dev"
	java -jar ${JAVA_OPTS} target/ussd000.jar

```

* Execute shell script to running application

```
	$> ksh runapps.ksh
	
	2017-08-10 20:54:40,061 main INFO Log4j appears to be running in a Servlet environment, but there's no log4j-web module available. If you want better web container support, please add the log4j-web JAR to your web archive or server lib directory.
	
	  .   ____          _            __ _ _
	 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
	( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
	 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
	  '  |____| .__|_| |_|_| |_\__, | / / / /
	 =========|_|==============|___/=/_/_/_/
	 :: Spring Boot ::        (v1.5.3.RELEASE)
	
	2017-08-10 20:54:45.662 [INFO ] INFO o.h.v.i.u.Version [background-preinit] - HV000001: Hibernate Validator 5.3.5.Final
	2017-08-10 20:54:50.266 [INFO ] INFO t.c.t.c.a.g.s.a.USSDApplication [main] - Starting USSDApplication v0.1.0 on bugkheab.local with PID 5972 (/Volumes/Macintosh_Data/Data/dtacGitWorkspace/spring-boot-workspace/poc-workspace/ussd000/target/ussd000.jar started by jet in /Volumes/Macintosh_Data/Data/dtacGitWorkspace/spring-boot-workspace/poc-workspace/ussd000)
	2017-08-10 20:54:50.267 [INFO ] INFO t.c.t.c.a.g.s.a.USSDApplication [main] - The following profiles are active: dev
	2017-08-10 20:54:50.332 [INFO ] INFO o.s.b.c.e.AnnotationConfigEmbeddedWebApplicationContext [main] - Refreshing org.springframework.boot.context.embedded.AnnotationConfigEmbeddedWebApplicationContext@5679c6c6: startup date [Thu Aug 10 20:54:50 ICT 2017]; root of context hierarchy
	2017-08-10 20:54:51.728 [INFO ] INFO o.s.b.c.e.t.TomcatEmbeddedServletContainer [main] - Tomcat initialized with port(s): 8082 (http)
	2017-08-10 20:54:51.745 [INFO ] INFO o.a.c.c.StandardService [main] - Starting service Tomcat
	2017-08-10 20:54:51.747 [INFO ] INFO o.a.c.c.StandardEngine [main] - Starting Servlet Engine: Apache Tomcat/8.5.14
	2017-08-10 20:54:51.849 [INFO ] INFO o.a.c.c.C.[.[.[/] [localhost-startStop-1] - Initializing Spring embedded WebApplicationContext
	2017-08-10 20:54:51.849 [INFO ] INFO o.s.w.c.ContextLoader [localhost-startStop-1] - Root WebApplicationContext: initialization completed in 1520 ms
	2017-08-10 20:54:52.030 [INFO ] INFO o.s.b.w.s.ServletRegistrationBean [localhost-startStop-1] - Mapping servlet: 'dispatcherServlet' to [/]
	2017-08-10 20:54:52.036 [INFO ] INFO o.s.b.w.s.FilterRegistrationBean [localhost-startStop-1] - Mapping filter: 'characterEncodingFilter' to: [/*]
	2017-08-10 20:54:52.036 [INFO ] INFO o.s.b.w.s.FilterRegistrationBean [localhost-startStop-1] - Mapping filter: 'hiddenHttpMethodFilter' to: [/*]
	2017-08-10 20:54:52.036 [INFO ] INFO o.s.b.w.s.FilterRegistrationBean [localhost-startStop-1] - Mapping filter: 'httpPutFormContentFilter' to: [/*]
	2017-08-10 20:54:52.036 [INFO ] INFO o.s.b.w.s.FilterRegistrationBean [localhost-startStop-1] - Mapping filter: 'requestContextFilter' to: [/*]
	2017-08-10 20:54:52.166 [INFO ] INFO t.c.t.c.a.g.u.USSDARestController [main] - deployed: USSDA
	2017-08-10 20:54:52.167 [INFO ] INFO t.c.t.c.a.g.u.USSDARestController [main] - LoggerTx Name=USSDA_TX
	2017-08-10 20:54:52.175 [INFO ] INFO t.c.t.c.a.g.u.USSDBRestController [main] - deployed: USSDB
	2017-08-10 20:54:52.175 [INFO ] INFO t.c.t.c.a.g.u.USSDBRestController [main] - LoggerTx Name=USSDB_TX
	2017-54-10 20:54:52.179 [INFO ] INFO th.co.tac.cns.app.gw.springboot.apps.USSDApplication$$EnhancerBySpringCGLIB$$3a424ffd [main] - Load SaltClientSystem
	log4j:WARN No appenders could be found for logger (org.reficio.ws.legacy.SchemaUtils).
	log4j:WARN Please initialize the log4j system properly.
	log4j:WARN See http://logging.apache.org/log4j/1.2/faq.html#noconfig for more info.
	2017-54-10 20:54:53.584 [INFO ] INFO th.co.tac.cns.app.gw.springboot.apps.USSDApplication$$EnhancerBySpringCGLIB$$3a424ffd [main] - Load UVCHttpClientSystem
	2017-54-10 20:54:53.594 [INFO ] INFO th.co.tac.cns.app.gw.springboot.apps.USSDApplication$$EnhancerBySpringCGLIB$$3a424ffd [main] - LoggerFactory=org.apache.logging.slf4j.Log4jLoggerFactory@62e136d3
	2017-54-10 20:54:53.594 [INFO ] INFO th.co.tac.cns.app.gw.springboot.apps.USSDApplication$$EnhancerBySpringCGLIB$$3a424ffd [main] - LoggerFactoryClass=org.apache.logging.slf4j.Log4jLoggerFactory
	2017-08-10 20:54:53.945 [INFO ] INFO o.s.w.s.m.m.a.RequestMappingHandlerAdapter [main] - Looking for @ControllerAdvice: org.springframework.boot.context.embedded.AnnotationConfigEmbeddedWebApplicationContext@5679c6c6: startup date [Thu Aug 10 20:54:50 ICT 2017]; root of context hierarchy
	2017-08-10 20:54:54.072 [INFO ] INFO o.s.w.s.m.m.a.RequestMappingHandlerMapping [main] - Mapped "{[/ussd-api/ussd-a-service],methods=[POST],produces=[text/xml]}" onto public org.springframework.http.ResponseEntity<java.lang.String> th.co.tac.cns.app.gw.ussdgwa.USSDARestController.post(javax.servlet.http.HttpServletRequest)
	2017-08-10 20:54:54.075 [INFO ] INFO o.s.w.s.m.m.a.RequestMappingHandlerMapping [main] - Mapped "{[/ussd-api/ussd-b-service],methods=[POST],produces=[text/xml]}" onto public org.springframework.http.ResponseEntity<java.lang.String> th.co.tac.cns.app.gw.ussdgwb.USSDBRestController.post(javax.servlet.http.HttpServletRequest)
	2017-08-10 20:54:54.078 [INFO ] INFO o.s.w.s.m.m.a.RequestMappingHandlerMapping [main] - Mapped "{[/error]}" onto public org.springframework.http.ResponseEntity<java.util.Map<java.lang.String, java.lang.Object>> org.springframework.boot.autoconfigure.web.BasicErrorController.error(javax.servlet.http.HttpServletRequest)
	2017-08-10 20:54:54.078 [INFO ] INFO o.s.w.s.m.m.a.RequestMappingHandlerMapping [main] - Mapped "{[/error],produces=[text/html]}" onto public org.springframework.web.servlet.ModelAndView org.springframework.boot.autoconfigure.web.BasicErrorController.errorHtml(javax.servlet.http.HttpServletRequest,javax.servlet.http.HttpServletResponse)
	2017-08-10 20:54:54.119 [INFO ] INFO o.s.w.s.h.SimpleUrlHandlerMapping [main] - Mapped URL path [/webjars/**] onto handler of type [class org.springframework.web.servlet.resource.ResourceHttpRequestHandler]
	2017-08-10 20:54:54.119 [INFO ] INFO o.s.w.s.h.SimpleUrlHandlerMapping [main] - Mapped URL path [/**] onto handler of type [class org.springframework.web.servlet.resource.ResourceHttpRequestHandler]
	2017-08-10 20:54:54.177 [INFO ] INFO o.s.w.s.h.SimpleUrlHandlerMapping [main] - Mapped URL path [/**/favicon.ico] onto handler of type [class org.springframework.web.servlet.resource.ResourceHttpRequestHandler]
	2017-08-10 20:54:54.413 [INFO ] INFO o.s.j.e.a.AnnotationMBeanExporter [main] - Registering beans for JMX exposure on startup
	2017-08-10 20:54:54.439 [INFO ] INFO o.a.c.h.Http11NioProtocol [main] - Initializing ProtocolHandler ["http-nio-8082"]
	2017-08-10 20:54:54.456 [INFO ] INFO o.a.c.h.Http11NioProtocol [main] - Starting ProtocolHandler ["http-nio-8082"]
	2017-08-10 20:54:54.485 [INFO ] INFO o.a.t.u.n.NioSelectorPool [main] - Using a shared selector for servlet write/read
	2017-08-10 20:54:54.514 [INFO ] INFO o.s.b.c.e.t.TomcatEmbeddedServletContainer [main] - Tomcat started on port(s): 8082 (http)
	2017-08-10 20:54:54.521 [INFO ] INFO t.c.t.c.a.g.s.a.USSDApplication [main] - Started USSDApplication in 19.738 seconds (JVM running for 25.969)
```