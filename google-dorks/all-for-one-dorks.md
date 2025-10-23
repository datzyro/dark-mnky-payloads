# Exposed Credentials & Authentication Data
## Usernames & Passwords
`site:example.com intext:"username" intext:"password" -git` 

`inurl:"/.git" example.com -github`

`site:example.com filetype:txt OR filetype:log "username" OR "password"`

`site:example.com inurl:admin OR inurl:login OR inurl:portal`

`site:pastebin.com "password" OR "login" OR "credentials"`

## Hardcoded Credentials in Configuration Files

`site:example.com filetype:env "DB_PASSWORD=" OR "DB_USER="`

`site:example.com filetype:json "AWS_ACCESS_KEY_ID=" OR "AWS_SECRET_ACCESS_KEY="`

`site:example.com filetype:config "password=" OR "apikey="`

## Exposed SSH Keys & Private Keys

`site:example.com filetype:pem OR filetype:key "BEGIN RSA PRIVATE KEY"`

`site:example.com "BEGIN OPENSSH PRIVATE KEY"`

# Internal & Confidential Documents

## Leaked Internal Documents
`site:example.com filetype:pdf OR filetype:doc OR filetype:xls "confidential" OR "internal use only"`

`site:example.com filetype:xls OR filetype:csv "employee salary" OR "payroll"`

`site:example.com ext:doc | ext:docx | ext:pdf | ext:xls | ext:xlsx | ext:csv | ext:sql | ext:txt | ext:conf | ext:key | ext:crt | ext:pfx | ext:py | ext:html | ext:sh`

`inurl:example.com "not for distribution" | confidential | "employee only" | proprietary | "top secret" | internal | private filetype:xls OR filetype:csv OR filetype:pdf`

`site:example.com filetype:docx "restricted" OR "not for public release"`

## Exposed Source Code Containing Secrets
`site:example.com filetype:php OR filetype:js OR filetype:env "DB_PASSWORD="`

`site:example.com intitle:"index of" "config.php"`

`site:example.com ext:sql | ext:mdb | ext:dbf`

`site:github.com "password" OR "api_key" OR "secret_key"`

# Financial & Payment Information
## Banking & Credit Card Data
`site:example.com intext:"credit card number" OR "CVV" OR "Visa" OR "MasterCard"`

`site:example.com intext:"bank account number" OR "routing number"`

`site:example.com filetype:xls OR filetype:csv "financial report"`

`site:example.com intitle:"index of" | ext:log | ext:swf | inurl:shell | inurl:backdoor | inurl:wso | inurl:cmd | shadow | passwd | boot.ini`

# Server & Configuration Leaks
## Sensitive Logs & Backup Files
`site:example.com filetype:log OR filetype:txt "error log" OR "debug log"`

`site:example.com ext:xml | ext:conf | ext:ini | ext:cfg | ext:env | ext:rdp | ext:reg`

`site:example.com intitle:"index of" "backup"`

`site:example.com ext:bkf | ext:bkp | ext:bak | ext:old | ext:backup`

`site:example.com filetype:sql "database dump" OR "backup"`

## Cloud & API Keys Exposure
`site:example.com filetype:json "google_api_key=" OR "firebase_api_key="`

`site:github.com "api_key" OR "access_token" OR "client_secret"`

# Misconfigured & Open Directories
## Open Directory Listings
`site:example.com intitle:"index of" "parent directory"`

`site:example.com intitle:"index of" "private" OR "confidential"`

`site:example.com intitle:"index of" "backup" OR "database"`

## Exposed Admin Panels & Dashboards
`site:example.com inurl:admin OR inurl:dashboard OR inurl:secure`

`site:example.com "admin panel" OR "restricted access"`

# Sensitive Emails & Contact Information
`site:example.com intext:"internal use only" OR "do not distribute"`

`site:example.com intext:"classified" OR "sensitive information"`

`site:example.com "employee email" OR "staff contact"`

# Errors and fingerprint based Recon 
`site:example.com intext:"sql syntax near" | intext:"syntax error has occurred" | intext:"unexpected end of SQL command" | intext:"Warning: mysql_connect()"`

`site:example.com "PHP Parse error" | "PHP Warning" | "PHP Error"`

`site:example.com inurl:wp-content | inurl:wp-includes`

`site:example.com | site:*.atlassian.net "telenor"`

`site:.s3.amazonaws.com | site:storage.googleapis.com | site:amazonaws.com "example"`
