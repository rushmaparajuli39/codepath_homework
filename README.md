# Week 7 & 8 Project: WordpressVsKali
Time Spent: **10** hours spent in total

> Objective: To find, analyze, recreate, and document three vulnerabilities affecting an old version of WordPress.

## Pentesting Report
### 1. CVE-2017-6817
Current Description
In WordPress before 4.7.3 (wp-includes/embed.php), there is authenticated Cross-Site Scripting (XSS) in YouTube URL Embeds.

- [ ] Summary: **WordPress 4.0-4.7.2 - Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds**
- Vulnerability types: XSS
- Tested in version: 4.2
- Fixed in version: 4.2.13

 - [ ] GIF Walkthrough: 
![1st-Rushma](https://user-images.githubusercontent.com/89615796/161604808-70a8901c-b0b2-4301-a3ee-d4c664f6f61d.gif)

- [ ] Steps to recreate: Create a post with a youtube video embedded into the post. The post is injected containing a simple script as:

    [embed src='https://youtube.com/embed/123\x3csvg onload=alert(20)\x3e'][/embed]

- [ ] Affected source code:
- [Link 1]shortcode_parse_atts

### 2. CVE 2019-17671
Current Description
In WordPress <= 5.2., there is a vulnerability that could allow an unauthenticated user to view private or draft posts due to an issue within WP_Query.

- [ ] Summary: **WordPress <= 5.2. - Unauthenticated View Private/Draft Posts

- Vulnerability types: IDOR/BYPASS
- Tested in version: 4.2
- Fixed in version: 4.2.25

 - [ ] GIF Walkthrough: 

![2nd-Rushma](https://user-images.githubusercontent.com/89615796/161607128-d79003c2-ae8e-4229-a05d-2a42b2463643.gif)

- [ ] Steps to recreate: Adding ?static=1 to a wordpress URL should leak its secret content. http://wpdistillery.vm/?static=1 will result in displaying all the draft, private, password protected and trashed pages.


- [ ] Affected source code:
- [Link 1]class-wp-query.php

### 3. CVE: 2017-5487
Current Description
In WordPress <= 4.7.1, an attacker thoroughly scans a web application to discover the login name of the WordPress based web application
  - [ ] Summary: **WordPress Core < 4.7.1 - Username Enumeration/IDOR
    - Vulnerability types: User Enumeration/IDOR
    - Tested in version: 4.2
    - Fixed in version: Version not applicable
  - [ ] GIF Walkthrough: 
  ![3rd-Rushma](https://user-images.githubusercontent.com/89615796/161609917-eae52699-6d4b-4c4e-b163-4dc07df2fa68.gif)

  
  - [ ] Steps to recreate: Open the wordpress site and add ?author=(number) at the end of the url, replacing (number) with an integer. When you view the page source, you can see the username.
  - [ ] Affected source code:
    - [Link 1](htaccess)
 
 
## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [ScreenToGif](https://www.screentogif.com/).

## Notes

The links contained a lot of information, and it was often tough to filter through it all to figure out how to carry out the exploit.
Also, as a MAC user, there is a bug with Virtual Box new version with ip address for host-only system so I encountered problem during installation too.

## License

    Copyright [2022] [Rushma Parajuli]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
