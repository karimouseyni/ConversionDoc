# Conversion Doc
Application de Conversion document

L'application permettra à un utilisateur de convertir d'un document vers un autre format.
Pour réaliser cela l'application sera décomposée en sous service :
- Service permettant d'uploader des fichier (et notification) + notification du processus de conversion
- Processus la conversion des documents + notification utilisateur(facultatif)
- Processus de suppression des URL après 5min
- Service permettant de télécharger un document converti
- Service permettant de retourner l'état des documents
- service permettant de retourner l'état des documents d'un client

# Dependences
## Template
    
```
<dependency>
    <groupId>org.thymeleaf</groupId>
    <artifactId>thymeleaf</artifactId>
    <version>3.0.9.RELEASE</version>
</dependency>
<dependency>
    <groupId>org.thymeleaf</groupId>
    <artifactId>thymeleaf-spring4</artifactId>
    <version>3.0.9.RELEASE</version>
</dependency>
<dependency>
    <groupId>nz.net.ultraq.thymeleaf</groupId>
    <artifactId>thymeleaf-layout-dialect</artifactId>
    <version>2.0.5</version>
</dependency>
```
## Conversion
```
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-pdf</artifactId>
    <version>18.9</version>
</dependency>
<dependency>
    <groupId>args4j</groupId>
    <artifactId>args4j</artifactId>
    <version>2.32</version>
</dependency>
<dependency>
    <groupId>org.docx4j</groupId>
    <artifactId>docx4j</artifactId>
    <version>3.2.1</version>
</dependency>
<dependency>
    <groupId>org.apache.poi</groupId>
    <artifactId>poi</artifactId>
    <version>3.12</version>
</dependency>
<dependency>
    <groupId>org.apache.poi</groupId>
    <artifactId>poi-ooxml</artifactId>
    <version>3.12</version>
</dependency>
<dependency>
    <groupId>org.apache.poi</groupId>
    <artifactId>poi-scratchpad</artifactId>
    <version>3.12</version>
</dependency>
<dependency>
    <groupId>fr.opensagres.xdocreport</groupId>
    <artifactId>org.apache.poi.xwpf.converter.pdf</artifactId>
    <version>1.0.5</version>
</dependency>
<dependency>
    <groupId>com.itextpdf</groupId>
    <artifactId>itextpdf</artifactId>
    <version>5.5.6</version>
</dependency>
<dependency>
    <groupId>fr.opensagres.xdocreport</groupId>
    <artifactId>org.odftoolkit.odfdom.converter.pdf</artifactId>
    <version>1.0.5</version>
</dependency>
<dependency>
    <groupId>fr.opensagres.xdocreport</groupId>
    <artifactId>fr.opensagres.xdocreport.itext.extension</artifactId>
    <version>1.0.5</version>
</dependency>
```
## Envoi email
```
<dependency>
    <groupId>com.sun.mail</groupId>
    <artifactId>javax.mail</artifactId>
    <version>1.6.1</version>
</dependency>
```
## Base de donnée
```
<dependency>
    <groupId>com.h2database</groupId>
    <artifactId>h2</artifactId>
    <scope>runtime</scope>
</dependency>
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-data-jpa</artifactId>
</dependency>
</dependencies>
```
## Js et Css 
```
<!--Webjars-->
<dependency>
    <groupId>org.webjars</groupId>
    <artifactId>bootstrap</artifactId>
    <version>3.3.7</version>
</dependency>
<dependency>
    <groupId>org.webjars</groupId>
    <artifactId>font-awesome</artifactId>
    <version>4.6.1</version>
</dependency>
<dependency>
    <groupId>org.webjars</groupId>
    <artifactId>fastclick</artifactId>
    <version>1.0.6</version>
</dependency>
<dependency>
    <groupId>org.webjars</groupId>
    <artifactId>jquery</artifactId>
    <version>2.2.3</version>
</dependency>
<dependency>
    <groupId>org.webjars.bower</groupId>
    <artifactId>nprogress</artifactId>
    <version>0.2.0</version>
</dependency>
<dependency>
    <groupId>org.webjars</groupId>
    <artifactId>webjars-locator</artifactId>
    <version>0.30</version>
</dependency>        
```       
# Configuration
## Docx4j
```properties
docx4j.Log4j.Configurator.disabled=true
```
## Log4j
```properties
#log4j.rootLogger=debug, stdout, R
log4j.rootLogger=OFF

log4j.appender.stdout=org.apache.log4j.ConsoleAppender
log4j.appender.stdout.layout=org.apache.log4j.PatternLayout

# Pattern to output the caller's file name and line number.
log4j.appender.stdout.layout.ConversionPattern=%5p [%t] (%F:%L) - %m%n

log4j.appender.R=org.apache.log4j.RollingFileAppender
log4j.appender.R.File=example.log

log4j.appender.R.MaxFileSize=100KB
# Keep one backup file
log4j.appender.R.MaxBackupIndex=1

log4j.appender.R.layout=org.apache.log4j.PatternLayout
log4j.appender.R.layout.ConversionPattern=%p %t %c - %m%n
```

# développement
Le développement de ce système sera mis en œuvre, sous le langage java en tout utilisant :
- Springs
- Une base de donnée Hibernet pour le stockage des donnée


