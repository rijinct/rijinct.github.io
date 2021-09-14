---
layout: post
title: The power of NiFi
subtitle: Securing NiFi
comments: true
---

Apache NiFi is an integrated data logistics platform for automating the movement of data between disparate systems. It provides real-time control that makes it easy to manage the movement of data between any source and any destination. It is data source agnostic, supporting disparate and distributed sources of differing formats, schemas, protocols, speeds and sizes such as machines, geo location devices, click streams, files, social feeds, log files and videos and more


## NiFi Security

**NIFI Authentication:**

NiFi supports Authentication and Authorization only if SSL is enabled.

NiFi supports below Authentication strategies

1. LDAP
2. Kerberos

NiFi supports following Authorization:

1. File-based policies (managed within NiFi)
2. Ranger-based policies (managed within Ranger)
3. Custom pluggable authorizer


**Configuring LDAP to Nifi: :**

Make the below changes in nifi.properties, authorizers.xml and login-identity-providers.xml 

In login-identity-providers.xml, uncomment and update the ldap-provider section as below: 
~~~
<provider>
<identifier>ldap-provider</identifier>
<class>org.apache.nifi.ldap.LdapProvider</class>
<property name="Authentication Strategy">SIMPLE</property>

<property name="Manager DN">CN=Rijin Thomas,OU=Researchers,OU=Users,OU=Company,DC=icd,DC=uw,DC=edu,DC=au</property>
<property name="Manager Password">******</property>

<property name="TLS - Keystore"></property>
<property name="TLS - Keystore Password"></property>
<property name="TLS - Keystore Type"></property>
<property name="TLS - Truststore"></property>
<property name="TLS - Truststore Password"></property>
<property name="TLS - Truststore Type"></property>
<property name="TLS - Client Auth"></property>
<property name="TLS - Protocol"></property>
<property name="TLS - Shutdown Gracefully"></property>

<property name="Referral Strategy">FOLLOW</property>
<property name="Connect Timeout">10 secs</property>
<property name="Read Timeout">10 secs</property>

<property name="Url">ldap://hodc01.ichr.uwa.edu.au</property>
<property name="User Search Base">OU=Company,DC=icd,DC=uw,DC=edu,DC=au</property>
<property name="User Search Filter">cn={0}</property>

<property name="Identity Strategy">USE_USERNAME</property>
<property name="Authentication Expiration">12 hours</property>
</provider>
}
foo(3)
~~~

In nifi.properties file, make the following changes:

~~~

         nifi.login.identity.provider.configuration.file=./conf/login-identity-providers.xml
         nifi.security.user.login.identity.provider=ldap-provider
~~~

And here is the same code with syntax highlighting:

```python
    def modify_ext_property(self, instrument_name, event_name):
        self.data_ext_property['forms[0]'] = instrument_name
        self.data_ext_property['events[0]'] = event_name
        if self.date_range_lst[0] != 'None':
            self.data_ext_property['dateRangeBegin'] = self.date_range_lst[0]
            self.data_ext_property['dateRangeEnd'] = self.date_range_lst[1]
        print('data_ext_property after modification -> {}'.format(self.data_ext_property))
```

```javascript
var foo = function(x) {
  return(x + 5);
}
foo(3)
```

And here is the same code yet again but with line numbers:

{% highlight javascript linenos %}
var foo = function(x) {
  return(x + 5);
}
foo(3)
{% endhighlight %}

## Boxes
You can add notification, warning and error boxes like this:

### Notification

{: .box-note}
**Note:** This is a notification box.

### Warning

{: .box-warning}
**Warning:** This is a warning box.

### Error

{: .box-error}
**Error:** This is an error box.
