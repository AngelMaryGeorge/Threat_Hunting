# Introduction to Threat Intelligence

Threat Intelligence is the analysis of data and information using tools and techniques to generate meaningful patterns on how to mitigate against potential risks associated with existing or emerging threats targeting organisations, industries, sectors or governments.

[Practical Analysis](./Introduction.md)

# Threat Intelligence Tools

## 1. [Urlscan.io](https://urlscan.io/)

Urlscan.io is a free service developed to assist in scanning and analysing websites. It is used to automate the process of browsing and crawling through websites to record activities and interactions.

## 2. [Abuse.ch](https://abuse.ch/)

Abuse.ch is a research project hosted by the Institue for Cybersecurity and Engineering at the Bern University of Applied Sciences in Switzerland. It was developed to identify and track malware and botnets through several operational platforms developed under the project.

These platforms are:

 - Malware Bazaar: A resource for sharing malware samples.
 - Feodo Tracker: A resource used to track botnet command and control (C2) infrastructure linked with Emotet, Dridex and TrickBot.
 - SSL Blacklist: A resource for collecting and providing a blocklist for malicious SSL certificates and JA3/JA3s fingerprints.
 - URL Haus: A resource for sharing malware distribution sites.
 - Threat Fox: A resource for sharing indicators of compromise (IOCs).

 ## 3. [PhishTool](https://www.phishtool.com/)

 PhishTool seeks to elevate the perception of phishing as a severe form of attack and provide a responsive means of email security. Through email analysis, security analysts can uncover email IOCs, prevent breaches and provide forensic reports that could be used in phishing containment and training engagements.

 ## 4. [Cisco Talos](https://talosintelligence.com/)

 IT and Cybersecurity companies collect massive amounts of information that could be used for threat analysis and intelligence. Being one of those companies, Cisco assembled a large team of security practitioners called Cisco Talos to provide actionable intelligence, visibility on indicators, and protection against emerging threats through data collected from their products. 

 [Practical Analysis](./Task-1.md)
 
# Yara

Yara can identify information based on both binary and textual patterns, such as hexadecimal and strings contained within a file. 
Rules are used to label these patterns. For example, Yara rules are frequently written to determine if a file is malicious or not, based upon the features - or patterns - it presents.

#### Examples of Yara Rules

 - To search a directory for all files containing "Hello World!"

 ```
rule helloworld_checker{
	strings:
		$hello_world = "Hello World!"
    condition:
		$hello_world
}
```

 - To match "Hello World" or "hello world" or "HELLO WORLD"

 ```
 rule helloworld_checker{
	strings:
		$hello_world = "Hello World!"
		$hello_world_lowercase = "hello world"
		$hello_world_uppercase = "HELLO WORLD"

	condition:
		any of them
 }

 ```

  - Rule rule matches if there are less than or equal to ten occurrences of the "Hello World!" string

  ```
 rule helloworld_checker{
	strings:
		$hello_world = "Hello World!"

	condition:
        #hello_world <= 10
}

```
 - Rule matches if both conditions are true

 ```
 rule helloworld_checker{
	strings:
		$hello_world = "Hello World!" 
        
        condition:
	        $hello_world and filesize < 10KB 
}

```

[Practical Analysis Using Loki](./Loki.md)
