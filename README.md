# bugbounty-dorks

Web Application https://reewardius.github.io/bugbounty-dorks/

# Google Dorks for Bug Bounty

A list of Google Dorks for Bug Bounty, Web Application Security, and Pentesting

[![Twitter URL](https://img.shields.io/twitter/url/https/twitter.com/reewardius.svg?style=social&label=Follow%20%40reewardius)](https://twitter.com/reewardius)
</p>

---
### Broad domain search w/ negative search

> site:example.com -www -shop

### Login Pages

> site:example.com inurl:login | inurl:logon | inurl:sign-in | inurl:signin

> site:example.com inurl:admin | administrator | adm | login | wp-login

### Backup Files

> site:example.com ext:bkf | ext:bkp | ext:bak | ext:old | ext:backup | ext:log

### Juicy Info

> site:example.com ext:txt | ext:conf | ext:cnf | ext:ini | ext:env | ext:sh | ext:swp | ext:old | ext:~ | ext:htpasswd | ext:htaccess | ext:sql | ext:csv | ext:.git-credentials | ext:yaml | ext:yml | ext:ppk | ext:pem | ext:json | ext:cfg | ext:xml | ext:ps1 | ext:reg | ext:inf | ext:rdp | ext:ora | ext:dbf | ext:mdb

> allintext:username|password|pass|email filetype:log site:example.com

> intitle:index of "wc.db" site:example.com

> intext:"index of" ".git" site:example.com

> site:example.com ext:doc | ext:xlsx | ext:docx | ext:odt | ext:pdf | ext:rtf | ext:sxw | ext:psw | ext:ppt | ext:pptx | ext:pps | ext:csv | ext:swf intext:password|pass|email|admin|user|offer|employee|order|internal|sensitive

> site:example.com jdbc

> site:example.com intitle:"index of /"

> intitle:"index of /" admin|user|portal|data|config|backup|password|email|employee|upload|uploads|download

> site:example.com inurl:admin/default.aspx

> site:example.com inurl:/wp-includes/uploads

> site:example.com inurl:/admin ext:config

> site:example.com inurl:wp- | inurl:wp-content | inurl:plugins | inurl:uploads | inurl:themes | inurl:download

> site:example.com inurl:readme | inurl:license | inurl:install | inurl:setup | inurl:config

> site:example.com inurl:shell | inurl:backdoor | inurl:wso | inurl:cmd | shadow | passwd | boot.ini | inurl:backdoor

> intitle:"index of" "config.php" site:example.com

> intext:"index of /" ".ovpn" site:example.com

> intitle:"index of" "database.sql" site:example.com

### SQL Injection Errors

> site:example.com intext:"sql syntax near" | intext:"syntax error has occurred" | intext:"incorrect syntax near" | intext:"unexpected end of SQL command" | intext:"Warning: mysql_connect()" | intext:"Warning: mysql_query()" | intext:"Warning: pg_connect()"

> intext:"error" | intext:"exception" site:"example.com"

### PHP extension w/ parameters

> site:example.com ext:php | ext: phtm | ext: phtml inurl:?

### Java extension w/ parameters

> site:example.com ext:jsp | ext:do | ext:action | ext:struts inurl:?

### NET extension w/ parameters

> site:example.com ext:aspx | ext:asa | ext:asp | ext:asax inurl:?

### Perl extension

> site:"example.com" ext:pl

### Other extensions

ext:cfm | ext:py | ext:rb

### App frameworks and their exposures

> site:example.com "Whoops! There was an error."

> site:example.com inurl:/frontend_dev.php/$

> site:example.com "SF_ROOT_DIR"

> site:example.com Application Trace + nil:NilClass (10%) TBD

> site:example.com "unexpected error" OR "Uncaught Exception" OR "fatal error" OR "Unknown column" OR "exception occurred"

> site:example.com employee offers

### XSS prone parameters

> inurl:lang= | inurl:name= | inurl:view= | inurl:name= | inurl:callback= | inurl:id= | inurl:q= | inurl:s= | inurl:keyword= | inurl:search= | inurl:page= | inurl:query= inurl:& site:example.com

### Open Redirect prone parameters

> inurl:page= | inurl:next= | inurl:host= | inurl:go= | inurl:goto= | inurl:file= | inurl:host= | inurl:redirect_to= | inurl:url= | inurl:redirect | inurl:src=http | inurl:r=http | inurl:return= | inurl:next= | inurl:redir= | inurl:http site:example.com

### SQLi Prone Parameters

> inurl:id= | inurl:pid= | inurl:page= | inurl:filter= | inurl:action= | inurl:register= | inurl:dir= | inurl:reg= inurl:& site:example.com

### SSRF Prone Parameters

> inurl:http= | inurl:resource= | inurl:resources= | inurl:url= | inurl:path= | inurl:host= | inurl:proxy= | inurl:html= | inurl:data= | inurl:domain=  | inurl:redirect= inurl:& site:example.com

### LFI Prone Parameters

> inurl:include= | inurl:page= | inurl:dir= | inurl:detail= | inurl:file= | inurl:folder= | inurl:locate= | inurl:doc= | inurl:conf= inurl:& site:example.com

### RCE Prone Parameters

> inurl:cmd | inurl:exec= | inurl:query= | inurl:code= | inurl:do= | inurl:run= | inurl:read=  | inurl:ping= inurl:& site:example.com

### High % inurl keywords

> inurl:config | inurl:env | inurl:setting | inurl:backup | inurl:admin | inurl:php site:example.com

### Sensitive Parameters

> inurl:email= | inurl:phone= | inurl:password= | inurl:secret= inurl:& site:example.com

### File Upload

> site:"example.com" "choose file"

### Code Leaks

> inurl:gitlab "example.com"

> inurl:https://trello.com intext:example.com

> site:atlassian.net "example.com"

> site:atlassian.net inurl:/servicedesk/customer/user/login "example.com"

> site:bitbucket.org "example.com"

> site:bitbucket.org inurl:example.com

> site:codebeautify.org "example.com"

> site:codepad.co "example.com"

> site:codepen.io "example.com"

> site:codeshare.io "example.com"

> site:coggle.it "example.com"

> site:firebaseio.com "example.com"

> site:gitter.im "example.com"

> site:google.com "example.com"

> site:box.com "example.com"

> site:jfrog.io "example.com"

> site:jsdelivr.net "example.com"

> site:jsfiddle.net "example.com"

> site:libraries.io "example.com"

> site:npm.runkit.com "example.com"

> site:npmjs.com "example.com"

> site:papaly.com "example.com"

> site:pastebin.com "example.com"

> site:prezi.com "example.com"

> site:productforums.google.com "example.com"

> site:repl.it "example.com"

> site:scribd.com "example.com"

> site:sharecode.io "example.com"

> site:trello.com "example.com"

> site:ycombinator.com "example.com"

> site:zoom.us inurl:"example.com"

### Cloud Storage

> site:s3.amazonaws.com "example.com"

> site:blob.core.windows.net "example.com"

> site:googleapis.com "example.com"

> site:drive.google.com "example.com"

> site:dev.azure.com "example.com"

> site:onedrive.live.com "example.com"

> site:digitaloceanspaces.com "example.com"

> site:sharepoint.com "example.com"

> site:amazonaws.com "example.com"

> inurl:www.dropbox.com/s/ "example.com"

> site:box.com/s "example.com"

> site:docs.google.com inurl:"/d/" "example.com"

### API DOCS

> inurl:apidocs | inurl:api-docs | inurl:swagger | inurl:api site:"example.com"

---

Medium articles for more dorks:

https://thegrayarea.tech/5-google-dorks-every-hacker-needs-to-know-fed21022a906

https://infosecwriteups.com/uncover-hidden-gems-in-the-cloud-with-google-dorks-8621e56a329d

https://infosecwriteups.com/10-google-dorks-for-sensitive-data-9454b09edc12

Top Parameters:

https://github.com/lutfumertceylan/top25-parameter

Proviesec dorks:

https://github.com/Proviesec/google-dorks
