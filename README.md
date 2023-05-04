# bugbounty-dorks

# Google Dorks for Bug Bounty

A list of Google Dorks for Bug Bounty, Web Application Security, and Pentesting

[![Twitter URL](https://img.shields.io/twitter/url/https/twitter.com/reewardius.svg?style=social&label=Follow%20%40reewardius)](https://twitter.com/TakSec)
</p>

---

### Broad domain search w/ negative search

> site:example.com -www -shop -share -ir -mfa

### PHP extension w/ parameters

> site:example.com ext:php inurl:?

### Disclosed XSS and Open Redirects

> site:openbugbounty.org inurl:reports intext:"example.com"

### Juicy Extensions

> site:"example[.]com" ext:log | ext:txt | ext:conf | ext:cnf | ext:ini | ext:env | ext:sh | ext:bak | ext:backup | ext:swp | ext:old | ext:~ | ext:git | ext:svn | ext:htpasswd | ext:htaccess

> site:"example[.]com" ext:pdf "username|user|pass|password|email|id"

> site:example.com ext:pdf "confidential"

> site:example.com ext:pdf "for internal use only"

> site:example.com ext:pdf "private"

> site:example.com ext:pdf "sensetive"

> site:example.com filename:.env

> site:example.com jdbc 

> site:example.com intitle:"index of" ext:sql|xls|xml|json|csv

> site:example.com "MYSQL_ROOT_PASSWORD:" ext:env OR ext:yml -git

> site:example.com inurl:admin filetype:db

> site:example.com inurl:"*admin | login" | inurl:.php | .asp

> filetype:log site:example.com

> inurl:passwd filetype:txt site:example.com

> intitle:"index of /*" site:example.com

> intitle:"index of /" (passwd | password.txt) site:example.com

> intitle:"index of /password" site:example.com

> intitle:"index of /admin" site:example.com

> intitle:"index of /" Parent Directory site:example.com

> site:example.com ext:txt | ext:doc | ext:docx | ext:odt | ext:pdf | ext:rtf | ext:sxw | ext:psw | ext:ppt | ext:pptx | ext:pps | ext:csv | ext:mdb

> intitle:"login" "admin" site:example.com

> site:example.com inurl:admin | administrator | adm | login | wp-login

> password filetype:docx site:example.com

> "index of /" */* site:example.com

> db_password filetype:env site:example.com

> intext:"index of /.git" "parent directory" site:example.com

> intitle:"index of" "properties.json" site:example.com

> intitle:"index of " "config/db" site:example.com

> inurl:"/private" intext:"index of /" "config"  site:example.com

> intitle:"index of" "config.php"  site:example.com

> intext:"index of /" ".ovpn" site:example.com

> intitle:"index of /" "styleci.yml" ".env" site:example.com

> intitle:"index of /" "docker-compose.yml" ".env" site:example.com

> intext:"index of" downloads" site:example.com

> inurl: "phpmyadmin/setup/" site:example.com

> intitle:"index of "conf.json" site:example.com

> site:example.com intext:"sql syntax near"

>  site:example.com intext:"syntax error has occurred" | intext:"incorrect syntax near" | intext:"unexpected end of SQL command" | intext:"Warning: mysql_connect()" | intext:"Warning: mysql_query()" | intext:"Warning: pg_connect()"

> site:example.com intext:"sql syntax near" |  intext:"incorrect syntax near"

> intitle:"index of "application.yml" site:example.com

> inurl:adminpanel site:example.com

> intitle:"index of" inurl:admin/php site:example.com

> inurl:"phpmyadmin/setup/" site:example.com

> inurl:ssh intitle:index of /files site:example.com

> intitle:"index of" "database.sql" site:example.com

> intext:"index of" smb.conf site:example.com

> intitle:"index of" inurl:wp-json index.json site:example.com

> intext:"index of" "config" site:example.com

> intitle:"index of /" intext:.db site:example.com

> intitle:index of "wc.db" site:example.com

> intext:"index of" ".git" site:example.com

> site:example.com intext:login intext:username intext:password

> site:example.com ext:ppt intext:password

> site:example.com filetype:xls inurl:"email.xls"

> allintext:username filetype:log site:example.com

> inurl:/proc/self/cwd site:example.com

> "index of" "database.sql.zip" site:example.com

> intitle:"index of" "WebServers.xml" site:example.com

> filetype:xls inurl:"email.xls" site:example.com

> intitle:"Index of" wp-admin site:example.com

> intitle:"index of" "admin/sql/" site:example.com

> intitle:"index of" "system/config" site:example.com

> site:example.com inurl:admin "@gmail.com"

> inurl:zoom.us/j and intext:scheduled for site:example.com

> allintitle:restricted filetype:doc site:example.com

> inurl:Dashboard.jspa intext:"Atlassian Jira Project Management Software" site:example.com

> filetype:txt site:example.com

### Code Leaks

> inurl:gitlab "example.com"

> site:atlassian.net "example.com"

> site:bitbucket.org "example.com"

> site:codebeautify.org "example.com"

> site:codepad.co "example.com"

> site:codepen.io "example.com"

> site:codeshare.io "example.com"

> site:coggle.it "example.com"

> site:gitter.im "example.com"

> site:google.com "example.com"

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

> inurl:https://trello.com AND intext:example.com

### Cloud Storage

> site:s3.amazonaws.com "example.com"

> site:blob.core.windows.net "example.com"

> site:googleapis.com "example.com"

> site:drive.google.com "example.com"

> site:dev.azure.com "example.com"

> site:onedrive.live.com "example.com"

> site:digitaloceanspaces.com "example.com"

> site:sharepoint.com "example.com"

> site:s3-external-1.amazonaws.com "example.com"

> site:s3.dualstack.us-east-1.amazonaws.com "example.com"

> site:dropbox.com/s "example.com"

> site:box.com/s "example.com"

> site:docs.google.com inurl:"/d/" "example.com"

### XSS prone parameters

> inurl:q= | inurl:s= | inurl:search= | inurl:query= inurl:& site:example.com

### Open Redirect prone parameters

> inurl:url= | inurl:return= | inurl:next= | inurl:redir= inurl:http site:example.com

### SQLi Prone Parameters

> inurl:id= | inurl:pid= | inurl:category= | inurl:cat= | inurl:action= | inurl:sid= | inurl:dir= inurl:& site:example.com

### SSRF Prone Parameters

> inurl:http | inurl:url= | inurl:path= | inurl:dest= | inurl:html= | inurl:data= | inurl:domain=  | inurl:page= inurl:& site:example.com

### LFI Prone Parameters

> inurl:include | inurl:dir | inurl:detail= | inurl:file= | inurl:folder= | inurl:inc= | inurl:locate= | inurl:doc= | inurl:conf= inurl:& site:example.com

### RCE Prone Parameters

> inurl:cmd | inurl:exec= | inurl:query= | inurl:code= | inurl:do= | inurl:run= | inurl:read=  | inurl:ping= inurl:& site:example.com

### High % inurl keywords

> inurl:config | inurl:env | inurl:setting | inurl:backup | inurl:admin | inurl:php site:example[.]com

### Sensitive Parameters

> inurl:email= | inurl:phone= | inurl:password= | inurl:secret= inurl:& site:example[.]com

### JFrog Artifactory

> site:jfrog.io "example.com"

### Firebase

> site:firebaseio.com "example.com"

### API Docs

> inurl:apidocs | inurl:api-docs | inurl:swagger | inurl:api-explorer site:"example[.]com"

### File upload endpoints

> site:example.com "choose file"

## Dorks that work better w/o domain

### Bug Bounty programs and Vulnerability Disclosure Programs

> "submit vulnerability report" | "powered by bugcrowd" | "powered by hackerone"

> site:*/security.txt "bounty"

### Apache Server Status Exposed

> site:*/server-status apache

### WordPress

> inurl:/wp-admin/admin-ajax.php

### Drupal

> intext:"Powered by" & intext:Drupal & inurl:user

### Joomla

> site:*/joomla/login


---

Medium articles for more dorks:

https://thegrayarea.tech/5-google-dorks-every-hacker-needs-to-know-fed21022a906

https://infosecwriteups.com/uncover-hidden-gems-in-the-cloud-with-google-dorks-8621e56a329d

https://infosecwriteups.com/10-google-dorks-for-sensitive-data-9454b09edc12

Top Parameters:

https://github.com/lutfumertceylan/top25-parameter

Proviesec dorks:

https://github.com/Proviesec/google-dorks
