# Phishing Analysis
<div align="center">
<img src="https://github.com/yelsanity/Phishing-E-mail/assets/142726793/df473391-5539-4b0c-8f01-693c1c924d7f" height="50%" width="60%" alt="phish"/>
</div>




<h2>Phishing</h2>
Phishing are common social engineering attacks, the goal of a phishing attempt is to trick the recipient to do the attacker's desired action, such as providing login credentials or other sensitive information. In social engineering, phishing attack vectors can be a phone call, a text message, or an email, our focus will be on email as the attack vector. 

<br />

<h2>Phishing Analysis Fundamentals </h2>
As a Security Analyst we need to know how to analyze emails to determine if it is malicious or benign.To do this we need to know all the components that makes up an email. Below are the components that which Emails are made out of.

- <h3>The Email Address -</h3>
  <b>identifies an email box to which messages are delivered</b>
  
   - <b>User Mailbox (or Username)</b>
   - <b>@</b>
   - <b>Domain</b>
   
  <b>example: "JohnD0e@Gmail.com"</b>
   
- <h3>Email Delivery</h3>
   <b>Email delivery is the process of successfully transferring an email message from the sender's email server to the recipient's email server.</b>
   
   <b>There are 3 specific protocols involved to facilitate the outgoing and incoming email messages, and they are briefly listed below.</b>
   
   - <b> **SMTP** (Simple Mail Transfer Protocol) - It is utilized to handle the sending of emails.</b>
   - <b> **POP3** (Post Office Protocol) - Is responsible transferring email between a client and a mail server.</b>
   - <b>IMAP (Internet Message Access Protocol) - Is responsible transferring email between a client and a mail server. </b>
  
<div align="center">
<img src="https://github.com/user-attachments/assets/cabd75fd-c4fd-47c6-8338-4a2044365c83" height="50%" width="60%" align="center" alt="Email Delivery"/>
<p>Below is an explanation of each numbered point from the above diagram:</p>
</div>
1.

         
- <h3>Email Headers</h3> 
- <h3>Email Body</h3>


<h2>Security Tools Used</h2>

- <b>Virus Total</b> 

<h2>Walk-through:</h2>

<p align="center">
Open the .eml file: <br/>
<img src="https://github.com/yelsanity/HowtoreadWiresharklogs/assets/142726793/f24838b2-7293-4ab1-88c7-20fef383841a"/>
<br />
<br />
After you open the .eml file an email will open:  <br/>
<img src="https://github.com/yelsanity/HowtoreadWiresharklogs/assets/142726793/6b738d00-fb37-4585-acdc-51504b754cf0" height="70%" width="70%" alt="Disk Sanitization Steps"/>
<br />
Upon opening the email we can immediately notice that sender's E-mail address and title of the mail is suspicious.
When you encounter E-mails like this beware and avoid immediately clicking buttons or links attached on it.We need to inspect the header for more info about this E-mail
<br />
<br />
<br />
INSPECTING THE HEADER<br/>
<br />
<br />
Go to file menu:
<br />
<img src="https://github.com/yelsanity/HowtoreadWiresharklogs/assets/142726793/9464a375-722e-4f77-88df-44a33c7e4151" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
Click properties: <br/>
<img src="https://github.com/yelsanity/HowtoreadWiresharklogs/assets/142726793/2f634af0-b5f1-4f58-8feb-424f9c4034be" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
Internet Headers:  <br/>
<img src="https://github.com/yelsanity/HowtoreadWiresharklogs/assets/142726793/7c843d5a-1e7a-4ed7-9457-656e592a1de2" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
Analyze the header to determine the return path:  <br/>
<img src="https://github.com/yelsanity/HowtoreadWiresharklogs/assets/142726793/1f15b15a-b4d5-40ee-9df6-8d6800b65f27" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<br />
As you have observe on the header section  we dont spot a single paypal domain reference in the header section<br />
thats suspicous already as the message is about your paypal account
<br />
<br />
<br />
DETERMINING THE DOMAIN NAME IN THIS E-MAIL:  <br/>
<br /> 
 Let'hover above the button to see the url where it will redirect us
<img src="https://github.com/yelsanity/HowtoreadWiresharklogs/assets/142726793/3fd81111-3d99-4d3a-93ae-44f94c1d9856" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<br />
<br />
<br />
Lets check the domain using Virust Total:  
<br/>
<img src="https://github.com/yelsanity/HowtoreadWiresharklogs/assets/142726793/822a84db-9568-49a7-96e2-10beb2f9c499" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<br />
No threat is detected here, but if we double check the URL there has a subdomain <br/>
<br />
<br />
<br />
Now lets include the subdomain andrun it again
<br />
<img src="https://github.com/yelsanity/HowtoreadWiresharklogs/assets/142726793/7e43110c-2106-4e03-ac91-90eb2e1a2f36" height="60%" width="60%" alt="Disk Sanitization Steps"/><br />
Now we have a ping of multiple detection
<br />
<br />
<br />
We can also observe the community reviews <br />
<img src="https://github.com/yelsanity/HowtoreadWiresharklogs/assets/142726793/0c43866e-3faf-485e-b438-c92db8faabbb" height="60%" width="60%" alt="Disk Sanitization Steps"/> <br />
Majority flagged it as suspicious
<br />
<br />
 <h2>Conclusion </h2>
</p> After we have Identified all our objectives we can therefore conclude that this is indeed a Phishing E-mail.The return path for the E-mail is not connected to any Paypal domain references,the URL domain is legitimate but the link of the CTA button redirect us to a subdomain that when we run through Virus Total, it is flagged as a Phishing E-mail.

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
