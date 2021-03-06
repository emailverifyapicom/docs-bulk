.. _Detailed Response Codes:

Email Verification Response Codes For Bulk Verification
=======================================================

.. _Main Status Codes:

Main Status Codes
^^^^^^^^^^^^^^^^^^^^^^^^^^
:Ok:
	Verification passes all checks including Syntax, :term:`DNS`, 
	:term:`MX`, Mailbox, Deep Server Configuration, :term:`Grey Listing`

:Bad:
	Verification fails checks for definitive reasons (e.g. mail box does not exist)
	
:Unknown:
	Conclusive verification result cannot be achieved due to mail server configuration 
	or anti-spam measures. See table \"Additional Status Codes\".

.. _Additional Status Codes:
	
Additional Status Codes
^^^^^^^^^^^^^^^^^^^^^^^
:None:
	No additional information is available.
	
	This status differs from other additional status codes as it should not be retried (the result will not change).
	
:AtSignNotFound:
	The required '@' sign is not found in email address.

:CatchAllConnectionFailure:
	The secondary catch all verification failed upon connection.
	
:CatchAllValidationTimeout:
	The secondary catch all validation timed out.
	
:DnsConnectionFailure:
	The DNS connection failed.
	
:DnsQueryTimout:
	The DNS service failed to respond (timeout). A typical example of this status code
	is when a DNS server on the target infrastructure is configured incorrectly.
	
:DomainIsInexistent:
	The domain (i.e. the bit after the '@' character) defined in the email address 
	does not exist, according to :term:`DNS` records.

	A domain that does not exist cannot have email boxes. A domain that does not 
	exist cannot have email boxes.

:DomainIsWellKnownDea:
	The domain is a well known Disposable Email Address :term:`DEA`.

	There are many services available that permit users to use a one-time 
	only email address. Typically, these email addresses are used by 
	individuals wishing to gain access to content or services requiring 
	registration of email addresses but same individuals not wishing to 
	divulge their true identities (e.g. permanent email addresses).

	:term:`DEA` addresses should not be regarded as valid for email 
	send purposes as it is unlikely that messages sent to :abbr:`DEA(Disposable Email Address)` 
	addresses will ever be read. :abbr:`DEA(Disposable Email Address)` 
	addresses should not be regarded as valid for email send purposes 
	as it is unlikely that messages sent to :term:`DEA` addresses will ever be read.

:DomainPartCompliancyFailure:
	The domain part compliancy failed.
	
:DoubleDotSequence:
	The email addresses domain contained double dots.
	
:IpBlockDetected: 
	An IP block has been detected.
	
:InvalidAddressLength:
	The email address is an invalid length.
	
:InvalidCharacterInSequence:
	The email address contains an invalid character.
	
:InvalidFoldingWhiteSpaceSequence:
	The email address contains a folding white space.
	
:InvalidLocalPartLength:
	The email address contains an invalid 
	`local  part <http://tools.ietf.org/html/rfc3696#section-3>`_ length.
	
:InvalidWordBoundaryStart:
	http://tools.ietf.org/html/rfc3696#section-3
	
:LocalSenderAddressRejected:
	The local sender address was rejected.
	
:MailboxFull:
	The mailbox is full.

	Mailboxes that are full are unable to receive any further email 
	messages until such time as the user empties the mail box or the 
	system administrator grants extra storage quota.

	Most full mailboxes usually indicate accounts that have been 
	abandoned by users and will therefore never be looked at again.

	We do not recommend sending emails to email addresses identified 
	as *full*.
	
:MailboxDoesNotExist:
	The mailbox does not exist.
	
	100% confidence that the mail box does not exist.
	
:MailboxTemporarilyUnavaible:
	The mail server is operating :term:`Grey Listing`. Whilst we endeavour to verify
	grey listed addresses, sometimes it is not possible whilst still offering timely
	verification results.
	
:NoMxServersFound:
	There are no mail servers defined for this domain, according to :term:`DNS`.
	
	Email addresses cannot be valid if there are no email servers 
	defined in :term:`DNS` for the domain.

:OperationCanceled:
	The operation was cancelled.
	
:ProxyConnectionTimeout:
	The proxy timed out.
	
:ServerDoesNotSupportInternationalMailboxes:
	The server does not support international mailboxes.
	
	International email boxes are those that use international 
	character sets such as Chinese / Kanji etc.
	
	International email boxes require systems in place for :term:`Punycode` 
	translation.

	Where these systems are not in place, email verification or delivery 
	is not possible.
	
	For further information see :term:`Punycode`.
	
:ServerIsCatchAll:
	The server is configured for *catch all* and responds to all 
	email verifications with a status of *Ok*.

	Mail servers can be configured with a policy known as *Catch All*. 
	Catch all redirects any email address sent to a particular 
	domain to a central email box for manual inspection. Catch all 
	configured servers cannot respond to requests for email address verification.
	
:SmtpConnectionFailure:
	The TCP connection to the target mail server failed.
	
:SmtpConnectionShutdown:
	The target mail server prematurely terminated the connection.
	
:SmtpConnectionTimeout:
	A timeout occurred whilst waiting for a connection to the target mail server.
	
:SmtpConnectionRefused:
	The SMTP connection was refused by the remote server. This status code applies
	to all :term:`Office 365` mail server, stopping verification, as these mail servers	
	all operate a catch-all policy.
	
:Success:
	Successful verification.
	
	100% confidence that the mail box exists.

:TcpSocketUnavailable:
	The TCP socket is unavailable for date exchange.
	
:TooManyAtSignsFound:
	Too many '@' signs found in email address.

	Only one '@' character is allowed in email addresses.
	
:UnableToBindToLocalIpAddress:
	Cannot bind local IP endpoint specified.
	
:UnexpectedQuotedPairSequence:
	http://tools.ietf.org/html/rfc3696#section-3

:UnhandledException:
	Transient service fault.

:Unknown:
	The reason for the verification result is unknown.
	
:PossibleSpamTrapDetected:
	A possible spam trap email address or domain has been detected.

	Spam traps are email addresses or domains deliberately placed on-line 
	in order to capture and flag potential spam based operations.

	Our advanced detection heuristics are capable of detecting likely 
	spam trap addresses or domains known to be associated with spam trap techniques.

	We do not recommend sending emails to addresses identified as associated 
	with known spam trap behaviour.

	Sending emails to known spam traps or domains will result in your :term:`ESP` 
	being subjected to email blocks from a :term:`DNS` :term:`Block List`..

	An :term:`ESP` cannot tolerate entries in a :term:`Block List` (as it adversely 
	affects email deliver-ability for all customers) and will actively refuse 
	to send emails on behalf of customers with a history of generating entries in a :term:`Block List`.