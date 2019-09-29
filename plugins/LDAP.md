**Descritption**

    This plugin allows the delegation of SonarQube authentication and authorization to an LDAP server (including LDAP Service of Active Directory).

**Installation**

    Download the LDAP plugin jar it into the SONARQUBE_HOME/extensions/plugins directory

    Configure the LDAP plugin by editing the SONARQUBE_HOME/conf/sonar.properties file.

    Restart the SonarQube server.


**Example of configuration**

	# LDAP configuration
    # General Configuration
    sonar.security.realm=LDAP
    ldap.url=ldap://dc2k87.ad.london.inspiredbroadcast.net:3268
    ldap.bindDn=ci-street
    ldap.bindPassword=C!5tr33t
    
    # User Configuration
    #ldap.user.baseDn=ou=Users
    #ldap.user.request=(&(objectClass=inetOrgPerson)(uid={login}))
    #ldap.user.realNameAttribute=cn
    #ldap.user.emailAttribute=mail
    
    # Group Configuration
    #ldap.group.baseDn=ou=Groups,dc=sonarsource,dc=com
    #ldap.group.request=(&(objectClass=posixGroup)(memberUid={uid}))
    
    sonar.security.realm=LDAP
    sonar.security.savePassword=true
    sonar.authenticator.createUsers=true
    ldap.url=ldap://dc2k87.ad.london.inspiredbroadcast.net:3268
    ldap.bindDn=service.sonar@ib
    ldap.bindPassword=Serv1ce5on4r
    ldap.authentication=simple
    sonar.authenticator.downcase=true

    ldap.user.baseDn=OU=INGG,DC=ad,DC=london,DC=inspiredbroadcast,DC=net
    ldap.user.request=(&(sAMAccountName={login})(objectclass=person))
    ldap.user.realNameAttribute=cn
    ldap.user.emailAttribute=mail

    #ldap.group.baseDn=OU=Groups,OU=INGG,DC=ad,DC=london,DC=inspiredbroadcast,DC=net
    #ldap.group.request=(&(objectClass=group)(member={dn}))
    #ldap.group.idAttribute=sAMAccountName

    sonar.security.localUsers=admin
