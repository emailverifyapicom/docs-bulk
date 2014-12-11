.. _emailverifyapi.com: https://upload.emailverifyapi.com

Features
========

Fanatical Service Quality Management (SQM)
------------------------------------------
`emailverifyapi.com`_ operational staff obsessively monitor services to 
ensure the best possible uptime and coverage.

Uptime and functional correctness is actively monitored on a minute by 
minute basis from multiple data centers dispersed across North America and Europe.

Multi Factor Verification
-------------------------
Progressive verification using multiple verification processes including:

 * Syntax checking
 * DNS checking
 * Mailbox checking
 
Unrivalled Coverage
-------------------
With more than 5 years experience and the benefit of owning our own 
software stack, `emailverifyapi.com`_ has refined its services over 
the years to provide good coverage not only of the easier :term:`B2B` 
domains but also the more technically tricky :term:`B2C` domains including:

 * Hotmail
 * Yahoo
 * AOL
 * Yandex

Spam Trap Detection
-------------------
After many years R&D, `emailverifyapi.com`_ has developed various \"secret sauces\" 
that can effectively detect and eliminate spam traps from several well known :term:`Block List`.

Disposable Email Address Detection
----------------------------------
Detect and eliminate :term:`DEA`.

What it does
------------
`emailverifyapi.com`_ is used to check email addresses in real-time. 
Not only are syntax and domain checked, but that the user mailbox 
is available too. This is the only way to know for sure if an email address is valid.

Additionally identified as part of the email verification process 
is extra information including:

* :term:`DEA`.
* :term:`Spam Trap`.


How it works
------------
Email addresses are verified using various filters and processes. 
As a high level overview, an email address submitted for verification 
goes thorough the following filters:

Syntax
	A basic inspection of the systax of the email address to see 
	if it looks valid. Work is done only using server :abbr:`CPU(Central Processing Unit)` 
	based on simple pattern matching algorithms.
	
DNS A
	Verifies a domain exists in :term:`DNS`. Domains that do not 
	exist in :term:`DNS` cannot have mail servers or email boxes.
	
	:term:`DNS` checks are performed over the network.
	
DNS MX
	Verify :term:`MX` records using :term:`DNS`. Domains that do not have 
	:term:`MX` records, have no mail servers and therefore no valid email boxes.
	
	:term:`MX` checks are performed over the network.

MailBox
	Verify email boxes with :term:`SMTP` checks.
	
	Connect to mail server and perform :term:`SMTP` 
	protocol to verify if mail box exists.
	
	This is the deepest level of verification. It is 
	performed over the network.