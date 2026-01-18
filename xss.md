# Cross-Site Scripting (XSS)

## What is XSS?
XSS is inserting malicious script into a website to obtain sensitive information, cookies, tokens and others.

## Types of XSS
- Reflected XSS
- Stored XSS
- DOM-based XSS

## Challenge 1: DOM XSS
<iframe src="javascript:alert(`xss`)">
This command is used in the search session and iframe was used as most of the application for HTML had bypass <script> command.

## Challenge 2: Bonus Payload
<iframe width="100%" height="166" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/771984076&color=%23ff5500&auto_play=true&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true"></iframe>
This command is used to inject thrid party video or audio. 
It is not using javascript but shows HTML vulnerability as iframe was used.
This will cause showing users harassment video, annoyance and misleading content.
**The coding challenge: this.searchValue = this.sanitizer.bypassSecurityTrustHtml(queryParam) [INCORRECT]
this.searchValue = queryParam [CORRECT] DON'T INCLUDE THIS bypassSecurity...

## Challenge 3: Reflected XSS
<iframe src="javascript:alert(`xss`)">
This challenge used above command in the track order webpage and inject the script by changing the url code after 'id='.
However, according to my research reflected is required to touch the server and had response but in this challenge
only pop up appears. It is processed by client-side JavaScript and written into the DOM. 
The challenge is categorized as reflected because the payload is non-persistent and executed immediately via a single request.

## Challenge 4: API-only XSS
<iframe src="javascript:alert(`xss`)"> 
I knew that no UI can be used and should be injected at the backend. 
Hence, I got an understanding from YouTube and learn the process. So, I used burp suite to inject the command. 
First, I found the api/quantity and send to the repeater. Then, I changed quantity to product and / to the product number I wanted.
So, I put /1 which shows apple juice. Content-Type: application/json is added above authorization as backend required this parses.
To check wheter the description can be changed, I first tried out random description.
And also change the GET to PUT command. Once response can be changed, I only paste the above command.

## Challenge 5: Client-side XSS Protection
<iframe src="javascript:alert(`xss`)">
Above command is used to inject malicious script when registering as a new user. I used burp suite when registering new email.
Then, I find the post part after clicking register. There is a part that showed email address and passwords.
I tried to change the email that I registered into the above iframe command by changing double quote to single quote. 
Then, xss alert is prompt but not successfull yet.
So, I send it to repeater and edit the command by using backslash and send it. Then, challenge solved.

### Impact

### Mitigation
- Sanitize input before storing
- Use content security policy (CSP)
