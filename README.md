# What


A tool providing an easy way to manage a DNS domain.

A user can reserve a (sub)domain if it is available and add entries like IPv4/v6
adresses, CNAME redirection, etc. 

The « view » part will be a web application, but a command line tool should be
easy to realize too.

# Why


For fun, because the project already exists in Perl 5 (netlib.re).
I wanted to use Perl 6 to discover the language, and to learn with a concrete
project, so I found this project adapted because of differents application
domains (file parsing, system, web part, database).

# How

## Grammar

The main part of this project is to write a grammar for parsing a DNS zone file.
As a result, we will obtain a "DNSZone" object, representing the content of this
file. 
This object will be modifiable (add/update/remove an entry) and will write the 
result in the corresponding DNS zone file.

This part should probably be a library, being available for other projects.

## Users

Each user need an account, and a subdomain is linked to.
A user should delegate a zone gestion to another user. We could create
groups/roles, etc.
It should be compatible with LDAP authentication.

This is quite classic.

## System

The system should manage many DNS server (potentially different software).
It will automatically (or by configuration file/database) choose master and
slaves.

# Documentation

Some sources for the grammar used.

## RFCs

"Domain names - concepts and facilities", Mockapetris, P., STD 13, RFC 1034, DOI 10.17487/RFC1034, November 1987, <http://www.rfc-editor.org/info/rfc1034>.
"Domain names - implementation and specification", Mockapetris, P., STD 13, RFC 1035, DOI 10.17487/RFC1035, November 1987, <http://www.rfc-editor.org/info/rfc1035>.
"Punycode: A Bootstring encoding of Unicode for Internationalized Domain Names in Applications (IDNA)", Costello, A., RFC 3492, DOI 10.17487/RFC3492, March 2003, <http://www.rfc-editor.org/info/rfc3492>.
"DoD Internet host table specification", Harrenstien, K., Stahl, M., and E. Feinler, RFC 952, DOI 10.17487/RFC0952, October 1985, <http://www.rfc-editor.org/info/rfc952>.

## Bind 9
ftp://ftp.isc.org/isc/bind9/cur/9.10/doc/arm/Bv9ARM.pdf