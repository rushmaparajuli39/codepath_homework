# Week 7 & 8 Project: WordpressVsKali
Time Spent: 10 hours

> Objective: To find, analyze, recreate, and document three vulnerabilities affecting an old version of WordPress.

##Pentesting Report
1. CVE-2017-6817
Current Description
In WordPress before 4.7.3 (wp-includes/embed.php), there is authenticated Cross-Site Scripting (XSS) in YouTube URL Embeds.
**WordPress 4.0-4.7.2 - Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds**

Vulnerability types: XSS
Tested in version: 4.2
Fixed in version: 4.2.13

#GIF
![1st-Rushma](https://user-images.githubusercontent.com/89615796/161604808-70a8901c-b0b2-4301-a3ee-d4c664f6f61d.gif)

Steps to recreate: Create a post with a youtube video embedded into the post. The post is injected containing a simple script as:

[embed src='https://youtube.com/embed/123\x3csvg onload=alert(20)\x3e'][/embed]

Affected source code:
shortcode_parse_atts

