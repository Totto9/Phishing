# Phishing Analysis

- Type of Challenge: Learning
- Duration: Two days
- Team challenge : solo


## Your Mission
As a SOC analyst, you have to analyze the 5 emails that your colleagues send you. You must determine which email appears to be phishing and write a report. Your report should include all your thoughts and print screens of all the tools you used 

### Phishing Fundamentals

First of all please do these two rooms of tryhackme :
- https://tryhackme.com/room/phishingemails1tryoe
- https://tryhackme.com/room/phishingemails2rytmuv


### Phishing Case
Your colleagues have provided you with emails in .eml format, ".eml" files are individual email files stored in Multipurpose Internet Mail Extensions (MIME) format. To scan .eml emails, you can use tools such as email clients (Outlook, Thunderbird, etc.), email viewing applications, or specialized tools such as email scanners.

Here are some general steps you can take to scan an .eml file:

- Open the .eml file in an email client or email viewing application. You can also open the .eml file with a text editor to see the source code of the email.
- Check the email headers to identify the sender, recipient, date and subject information. You may also find additional information, such as the mail servers involved in the transmission of the message.
- Check the content of the email for signs of phishing, such as suspicious links or requests for sensitive data.
- Check attachments for malicious files, such as macros or scripts.
- Use email analysis tools to extract additional information from the email, such as IP addresses of email servers or additional headers.

**In your report, you must at least answer all the questions in the list below :**

- What is the email's timestamp? 
- Who is the email from?
- What is his email address?
- What email address will receive a reply to this email? 
- What brand was this email tailored to impersonate?
- What is the originating IP? Defang the IP address. 
- What do you think will be a domain of interest? Defang the domain.
- What is the shortened URL? Defang the URL.
- Do you think this is a phishing email?

# TryHackMe Phishing Analysis Fundamentals

## TryHackMe Phishing Emails 1

## Task 1 Introduction

No answer needed

## Task 2 The Email Address

Email dates back to what time frame? 
1970’s

## Task 3 Email Delivery

What port is classified as Secure Transport for SMTP? 

-(SMTP stands for Simple Mail Transfer Protocol, a standard protocol for sending email messages between mail servers)
465
What port is classified as Secure Transport for IMAP?

-(IMAP stands for Internet Message Access Protocol, a standard protocol for retrieving and managing email messages on a mail server)
993
What port is classified as Secure Transport for POP3?

-(POP3 stands for Post Office Protocol version 3, a standard protocol for retrieving email from a mail server)
995

## Task 4 Email Headers

What email header is the same as "Reply-to"?

Return-Path
Once you find the email sender's IP address, where can you retrieve more information about the IP?

http://www.arin.net

## Task 5 Email Body

In the above screenshots, what is the URI of the blocked image? 

https://i.imgur.com/LSWOtDI.png

In the above screenshots, what is the name of the PDF attachment?

payment-updateid.pdf

In the attached virtual machine, view the information in email2.txt and reconstruct the PDF using the 
base64 data. What is the text within the PDF?

THM{BENIGN_PDF_ATTACHMENT}



How I did it?

i logged on to my virtual machine. i opened my email file as well as the cyberchef file. i simply copied and pasted (crtl a) the contents of my file into input, deleting the content at the top and at the end. 
In the operation category, i used the From Base64 option, which i slipped into my recipe.

I opened the terminal 

ls, 

cd desktop, 

cd email samples,
 ls 
copy the text open another text editor, 

deleting the header and last line. 
I saved it as emailtest.txt
back to terminal
ls 
i logged on to my virtual machine. i opened my email file as well as the cyberchef file. i simply copied and pasted (crtl a) the contents of my file into input, deleting the content at the top. in the operation category, i used the From Base64 option, which i slipped into my recipe.

I opened the terminal 
ls, cd desktop, cd email samples, ls 
copy the text open another text editor, deleting the header and last line. I saved it as emailtest.txt
back to terminal
ls 
cat email2.txt | base64 -d emailtest.txt > emailtest.pdf
The command "cat email2.txt | base64 -d emailtest.txt > emailtest.pdf" (dash d) decodes the content of the "email2.txt" file from Base64 and redirects it to the "emailtest.pdf" file.

What we did right here?
We cated it the content of email2.txt so our text document with just the base64 in it, we pipped it we send it a pipe is pretty much like send it to base64 dash d which means decode, decode what? You might ask … decode emailtest.txt so this file we decoding it with dash d option and give me the output the greater than sign is the output into emailtest.pdf 


cat emailtest.pdf
we should have our flag
(open my file in the folder)

Task 6 Types of Phishing

What trusted entity is this email masquerading as?

Home Depot
What is the sender's email?

support@teckbe.com
What is the subject line? 

Order Placed : Your Order ID OD2321657089291 Placed Successfully

How?

open email3.eml with Thunderbird Mail

copy the subject 

open with Clipboard

copy and paste 

What is the URL ink for - CLICK HERE? (Enter the defanged URL)

hxxp[://]t[.]teckbe[.]com/p/?j3=EOowFcEwFHl6EOAyFcoUFVTVEchwFHlUFOo6lVTTDcATE7oUE7AUET==

open  Email3.eml 

copy the link http://  change the http to hxxp

put the link http in Input

select Recipe select Delang Url you’ll get the answer


## Task 7 Conclusion

What is BEC?

Business Email Compromise
