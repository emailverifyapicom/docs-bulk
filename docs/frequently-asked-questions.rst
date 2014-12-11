.. _emailverifyapi.com: https://upload.emailverifyapi.com

Frequently Asked Questions
==========================

How fast is it?
---------------
Please allow up to 24 hours for a list to process.

How do I get emails into the system?
------------------------------------
Upload any text (.txt) or CSV (.csv) file that contains email addresses. This includes Excel (export as .csv), Outlook (export as .CSV) or any other application that can support exporting as text (almost all applications support this). Your files can contain extra data fields, we simply append our results to the end of your existing file.

How do I get results out of the system?
---------------------------------------
You can export results in the same format that you imported them.

Are there any emails that can’t be checked?
-------------------------------------------
For servers that we know give problems, such as those that give false positives (catch-all), we flag the email address appropriately.

How often should I check email addresses?
-----------------------------------------
For large lists (i.e. > 10,000), we suggest checking every 2 weeks. Smaller lists can be checked monthly

Email addresses are always changing. People change email addresses as they (for example):
 * Move Internet providers
 * Move to a new employer
 * Change name (e.g. after getting married)

If your business relies on email lists for its marketing, it’s important that you keep the lists current and “clean” to maximize your target potential and reduce the overheads associated with managing too many “bounced” emails. This is why we recommend frequent checking.

How do I sign up?
-----------------
To get started `create a new account <https://upload.emailverifyapi.com/index.php>`_ and upload your list.

How secure is my data?
----------------------
Very. We take your security and confidentiality seriously. We know that your email lists are confidential and we do everything we can to make sure that they stay that way!

Your data is held securely in US and UK data centers. As well as physical security of “locked” server rooms, we use strong password security in our software services. This means that no-one other than you can see your data.

Also, if you choose to cancel your plan at any time, we undertake to destroy / delete your data so that it cannot be retrieved or viewed by any other parties.

Do you share my email lists or use them in any other way?
---------------------------------------------------------
No. No-one other than you has access to your data / email lists.

What browsers do you support?
-----------------------------
Generally, anything that is younger (as of December 2014) than 7 years old. Including:
 * Safari
 * Internet Explorer (version 7+)
 * Firefox (version 2+)
 * Chrome
 * Opera
As this is an Internet based service, it means that it runs happily on any operating system including Mac, PC, Linux, Unix etc.

Can it do Hotmail?
------------------
Yes.

Can it do Yahoo?
----------------
Yes. Based on our own internal testing `emailverifyapi.com`_ is currently the only email verification service to offer effective and repeatable coverage for Yahoo addresses.

Can it do Yandex?
-----------------
Yes it can.

Can it find spam traps?
-----------------------
Partially.

A :term:`Spam Trap` is a moving target. In theory (and indeed in practice) anyone can setup a :term:`Block List` and start putting spam traps into the wild.

`emailverifyapi.com`_ has :term:`Spam Trap` detection capabilities that covers several of the well known block lists. Whilst it is not possible to deliver 100% coverage of all spam traps from all block lists, `emailverifyapi.com`_ provides the best :term:`Spam Trap` detection capabilities available.

How does it work?
-----------------
At a basic conceptual level, the process of verifying email addresses is very simple. Google for \"Send email using telnet\" for a quick and general overview of how it's done. To verify an email address without sending an email, simply go as far as the \"RCPT TO\" stage and parse the response code. That's the easy bit and can be accomplished in just a couple of dozen lines of a PHP script!

The hard bit is dealing with mail services that are intrinsically configured to work against the process of email verification or any similar SMTP based activity. The reason that any email / :term:`SMTP` process is difficult from a client perspective is that mail services need to protect themselves from an ever increasing landscape of abuse including spam and :term:`DDoS` attacks.

`emailverifyapi.com`_'s strength in dealing with the \"hard bit\" of email verification comes from years of experience in doing email verification together with our complete ownership of our :term:`SMTP` verification software stack together with an extensive cloud based infrastructure. That's why `emailverifyapi.com`_ can do the \"hard bits\" best and offer outstanding coverage on the more difficult domains such as Yahoo and Hotmail.

Can I get blacklisted using this service?
-------------------------------------
No. It's `emailverifyapi.com`_ infrastructure that does the work.

Will anyone know that I am verifying their email address?
---------------------------------------------------------
No. It's `emailverifyapi.com`_ infrastructure that does the work.

Your service says an address is OK and I know it's Bad (or vice versa)?
-----------------------------------------------------------------------
`emailverifyapi.com`_ queries mail servers in real time. Mail servers respond with one of 2 possible answers for a given email address:

 * Yes, the email address exists - SMTP code 2xx
 * No, the email address doe not exist - SMTP code 5xx

`emailverifyapi.com`_ uses the above response codes to determine if an email address is valid or not and reports this back to you.

This method of determining email address validity works in >99% cases. However, nothing is guaranteed. In a small number of cases it is possible for a mail server to report one thing on email verification and do something different on trying to deliver an email to the email address verified.

For example, say we take an email address of "this.seems.to.verify@hotmail.com" to send to. We are sending from a fictitious email address "my.sending.account@gmail.com".

"this.seems.to.verify@hotmail.com" reports with status code of "OK" from the email verification service. However, when you send an email to "this.seems.to.verify@hotmail.com", the email bounces. 
Further inspection of the bounced email Non Delivery Report (NDR) headers show something like the following:

:: 

	Delivered-To: my.sending.account@gmail.com
	Received: by 10.107.174.134 with SMTP id n6csp24867ioo;
			Sat, 6 Jun 2014 03:57:29 -0800 (PST)
	X-Received: by 10.202.4.5 with SMTP id 5mr1335105oie.22.1417867048986;
			Sat, 06 Jun 2014 03:57:28 -0800 (PST)
	Return-Path: <>
	Received: from SNT004-OMC2S34.hotmail.com (snt004-omc2s34.hotmail.com. [65.55.90.109])
			by mx.google.com with ESMTPS id ws5si21632759obb.102.2014.12.06.03.57.28
			for <my.sending.account@gmail.com>
			(version=TLSv1.2 cipher=ECDHE-RSA-AES128-SHA bits=128/128);
			Fri, 6 Jun 2014 03:57:28 -0800 (PST)
	Received-SPF: none (google.com: SNT004-OMC2S34.hotmail.com does not designate permitted sender hosts) client-ip=65.55.90.109;
	Authentication-Results: mx.google.com;
		   spf=none (google.com: SNT004-OMC2S34.hotmail.com does not designate permitted sender hosts) smtp.mail=
	Received: from SNT004-MC2F40.hotmail.com ([65.55.90.73]) by SNT004-OMC2S34.hotmail.com over TLS secured channel with Microsoft SMTPSVC(7.5.7601.22751);
		 Fri, 6 Jun 2014 03:57:28 -0800
	From: postmaster@hotmail.com
	To: my.sending.account@gmail.com
	Date: Fri, 6 Jun 2014 03:57:28 -0800
	MIME-Version: 1.0
	Content-Type: multipart/report; report-type=delivery-status;
		boundary="9B095B5ADSN=_01D010AABCE2C5CC0008C930SNT004?MC2F40.ho"
	X-DSNContext: 335a7efd - 4481 - 00000001 - 80040546
	Message-ID: <mjZ7zgTpi00029250@SNT004-MC2F40.hotmail.com>
	Subject: Delivery Status Notification (Failure)
	Return-Path: <>
	X-OriginalArrivalTime: 06 Jun 2014 11:57:28.0142 (UTC) FILETIME=[CEAD2EE0:01D0114B]

	This is a MIME-formatted message.  
	Portions of this message may be unreadable without a MIME-capable mail program.

	--9B095B5ADSN=_01D010AABCE2C5CC0008C930SNT004?MC2F40.ho
	Content-Type: text/plain; charset=unicode-1-1-utf-7

	This is an automatically generated Delivery Status Notification.

	Delivery to the following recipients failed.

		   this.seems.to.verify@hotmail.com


The email header of the NDR shows that Hotmail thinks the email address is invalid as far as sending to this address is concerned. 
However, Hotmail reports that the same email address is valid as far as the email verification activity performed by `emailverifyapi.com`_.

The discrepancy in verification results versus mail send is with the Hotmail infrastructure reporting one thing but doing the exact opposite. 
This behaviour occasionally (particularly from Hotmail) is seen in a small amount of cases and is attributable to internal Hotmail (or other mail services) system anomalies.

The majority (>99%) of email verification status versus mail send is consistent. However there are some edge cases caused by system faults in the mail service providers themselves. 
For these small number of cases, there is nothing that can be done at the email verification stage.

How do I cancel a subscription?
-------------------------------
For pay as you go accounts, the account is free and you just pay when you need it.

For subscription plans, you simply need to contact us via the support button in your account dashboard, and your cancellation will take effect at the end of the month. Please note that subscription plans have a minimum 2 month period, after that you can cancel at any time.

Our service is so good that we hope that you won’t need to cancel! However, if you do, we are proud of our simple cancellation process. Unlike many other companies, there are no hassles with fine print and tricky notice periods.

Once you’ve cancelled your service, we’ll disable your account and make sure that all your data is securely disposed of (deleted).