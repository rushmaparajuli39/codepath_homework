# Project 8 - Pentesting Live Targets

Time spent: **5** hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:

* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

## Blue

Vulnerability #1:  Session Hijacking/Fixation

Description: In the brave and safari browsers, I opened two instances of the login page. I copied the session id from one of the browsers. With the session id I copied, I altered the session id for another browser. The other browser was able to log in without having to use the login credentials.

![sessionid](https://user-images.githubusercontent.com/89615796/161626280-26ed245f-10e0-4d7a-bf43-db70df0fef6f.gif)


Vulnerability #2: SQL Injection (SQLi)
Description: The salesperson info page is vulnerable to SQL injection. This will cause the site to wait for 15 seconds before processing the request.
Putting the following SQL script onto the URL will cause the site to delay by 15 seconds.
  ?id=1' or sleep(15)=0--'

![sqlinjection](https://user-images.githubusercontent.com/89615796/161628591-e74d5242-a724-4c77-95d9-56e085fb81ca.gif)


## Green

Vulnerability #1: Username Enumeration

Description: You'll get an error if you input the right username "jmonroe99" or "pperson" but the wrong password. Upon closer examination of the error, we see that it is covered by class="failure." Error returns class="failed" when an incorrect username is supplied.

![userenumeration](https://user-images.githubusercontent.com/89615796/161630664-aec335bf-3c15-4120-8ea0-65b0713be855.gif)



Vulnerability #2: Cross-Site Scripting (XSS)

Description: I log into the admin area and look through the CMS in order to "spring the trap" and find out if my attack succeeded.After opening the contact form, I put the malicious code inside the form. 
  <script>alert('Rushma found the XSS!');</script>

![cross-sitescripting](https://user-images.githubusercontent.com/89615796/161633433-5e092dd1-4549-4748-acdb-62a6b22fb7a9.gif)


## Red
Vulnerability #1:  Insecure Direct Object Reference (IDOR)
Description: When you view the salesperson info, you can put ?id=10 or ?id=11 to view hidden information.

![idor](https://user-images.githubusercontent.com/89615796/161633992-a7b8a1d1-d559-4201-be23-b5602f93ba20.gif)

Vulnerability #2: Cross-Site Request Forgery (CSRF)

Description:

<img src="red-vuln2.gif">


## Notes

Describe any challenges encountered while doing the work
