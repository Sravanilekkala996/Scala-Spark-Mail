# ScalaMail
Scala utility to send mail 
This utility can be used to send Spark job failure message in mail. This Utility uses smtp protocol to send mail.
It is very easy to use you need to create a object and provide a complete path of Configuratin file where you need to mentioned 
all properties mentioned in application.conf file.


**Library Dependencies**

`libraryDependencies ++= Seq(`

  `"com.typesafe" % "config" % "1.3.3",`
  
  `"org.scala-lang" % "scala-compiler" % "2.11.12",`
  
 ` "org.json4s" %% "json4s-core" % "3.5.3",`
  
  `"javax.mail" % "mail" % "1.4.7"`

`)`

**Version**
* Scala "2.11.12"

# How to Use in Program
* Download attached Jar or src code and compile it with required dependencies
* Add this Jar dependencies in Spark Project (in Build.sbt) like below:
  
  `"com.spark.mail" %% "Email" % "0.0.1" from "file:///<path of Jar>/email_2.11-0.0.1.jar"`
  
* Import method in Scala Object or Class
* Initialize Email Object as below
   
   `val msg = "Spark Job failed" //you can initialize msg as exception of failure`
   
   `val Emailobj = new Email(<path of Conf file>)`
   
   `Emailobj.sendMail(sparkSession.sparkContext.applicationId,msg)`