---
title: Jenkins Script
---

```java
import com.cloudbees.plugins.credentials.domains.*
import com.cloudbees.plugins.credentials.common.*
import org.jenkinsci.plugins.plaincredentials.*
import com.cloudbees.jenkins.plugins.sshcredentials.*

// set Credentials domain name (null means is it global)
domainName = null

credentialsStore = Jenkins.instance.getExtensionList('com.cloudbees.plugins.credentials.SystemCredentialsProvider')[0]?.getStore()
domain = new Domain(domainName, null, Collections.<DomainSpecification>emptyList())

def jsonBuilder = new groovy.json.JsonBuilder()
jsonBuilder {
  "StandardUsernamePasswordCredentials" credentialsStore?.getCredentials(domain).collect {
    if( it instanceof StandardUsernamePasswordCredentials ) [ 
      ID:    it.id, 
      Scope: it.scope,
      UserName: it.username,
      Password: it.password?.plainText,
      Description: it.description,
      
    ] 
  }.findAll{ it != null }
  
  "SSHUserPrivateKey" credentialsStore?.getCredentials(domain).collect {
    if( it instanceof SSHUserPrivateKey ) [ 
      ID:    it.id, 
      Scope: it.scope,
      Passphrase: it.passphrase?.plainText,
      PrivateKeys: it.privateKeys,
      Description: it.description,
   ] 
  }.findAll{ it != null }
  
  "StringCredentials" credentialsStore?.getCredentials(domain).collect {
    if( it instanceof StringCredentials ) [ 
      ID:    it.id, 
      Scope: it.scope,
      Secret: it.secret?.plainText,
      Description: it.description,
   ] 
  }.findAll{ it != null }
    
  "FileCredentials" credentialsStore?.getCredentials(domain).collect {
    if( it instanceof FileCredentials ) [ 
      ID:    it.id, 
      Scope: it.scope,
      FileContent: it.content?.text,
      Description: it.description,
   ] 
  }.findAll{ it != null }
}

println jsonBuilder.toPrettyString()

println( "\n" )
println( "In case a new credential type, that was not yet included, apperas in your Jenkins, you can utilize the following information to add that block quickly to the list." )
println( "Do not forget to exclude said credential type from the outpiut below as well." )

jsonBuilder {
   credentialsStore?.getCredentials(domain).collect {
    if( !( it instanceof StandardUsernamePasswordCredentials || it instanceof SSHUserPrivateKey || it instanceof StringCredentials || it instanceof FileCredentials ) ) [
      ID:    it.id, 
      ClassName: it.class.name,
      InterfaceImplementations: it.class.interfaces.name,
      DeclaredMethods: it.class.declaredMethods.name,
      Scope: it.scope,
      Description: it.description,
    ] 
  }.findAll{ it != null }
}

println jsonBuilder.toPrettyString()
```