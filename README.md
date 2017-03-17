Django Active Directory Auth Demo
=================================

# Configuration
To start set the `AUTH_LDAP_SERVER_URI` to your LDAP/ADS server. For example: `AUTH_LDAP_SERVER_URI = "ldap://ads.example.com:389"`

We use a dedicated user to bind to the LDAP server and execute LDAP query to the server. 
To do set set: `AUTH_LDAP_BIND_DN` en `AUTH_LDAP_BIND_PASSWORD`. If you use an anonymous user you can remove these settings,

`AUTH_LDAP_USER_SEARCH` is set to search for `(sAMAccountName=%(user)s)`, which should be fine for searching Microsoft ADS. 
You may need to change this if you are using another LDAP provider.

# Demo
A standard `python manage.py runserver` will start the server at port 8000. Opening [http://localhost:8000] asks you to login with 
your ADS credentials. You can see the generated query and population of the database tables in the console output. 


