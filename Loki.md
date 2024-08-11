# Scenario

You are the security analyst for a mid-size law firm. A co-worker discovered suspicious files on a web server within your organization. These files were discovered while performing updates to the corporate website. The files have been copied to your machine for analysis. The files are located in the suspicious-files directory. Use Loki to answer the questions below.


1. Scan file 1. Does Loki detect this file as suspicious/malicious or benign?

 ![alt text](image-6.png)

 - Suspicious

2. What Yara rule did it match on?

 - webshell_metaslsoft

3. What does Loki classify this file as?

 - Web shell

4. Based on the output, what string within the Yara rule did it match on?

 - str1

5. What is the name and version of this hack tool?

 - b374k 2.2

6. Inspect the actual Yara file that flagged file 1. Within this rule, how many strings are there to flag this file?

 - 1

 ![alt text](image-5.png)

