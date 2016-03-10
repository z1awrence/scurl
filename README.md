# scurl
This is a secure version of curl I wrote for my final project in cs255 (Cryptography).
Standard curl has many vulnerabilities, most of which are certificate verification attacks. I implemented the program with this in mind, testing on several thousand sites.
I will soon update the repo to contain my test files.

Simply run ./scurl --some-flag https://www.example.com in terminal to obtain the html for a page. I list the valid flags and their meaning below:

• --tlsv1.0, --tlsv1.1, --tlsv1.2, --sslv3, -3 . Runs TLSv1.2 by default

• --ciphers. Which ciphers to use in connection. I.E. 
-ciphers DHE-DSS-AES256-SHA:DH-RSA-AES256-SHA https://www.stanford.edu/

• --crlfile. Refuses any certificates with one of the offending serial numbers.

• --cacert. Uses file as root CA

• --allow-stale-certs N. When a user invokes scurl with this option with an argument N, scurl will fetch the url if
(a) C is an otherwise valid certificate that has expired
and (b) C expired within the past N days. The argument N to this option must be a nonnegative
integer. If this option is used several times, the last one will be used.

• --pinnedpublickey <filename> 

See the curl manpage for more details on any of the flags.
