# (All) DNS Resource Records

In this directory you will find `bind(8)` DNS zone
files used by `panix.netmeister.org` to serve a
reasonable looking entry for every defined DNS
Resource Record (RR).

That is, for each RR `<rr>`, there exists an RR of
type `<rr>` under `<rr>.dns.netmeister.org.`

In addition, each RR has an accompanying TXT record
summarizing the purpose of the RR as well as which RFC
the record was defined in (earliest and latest), and a
TXT record providing the format of the RDATA in
question.

This allows you to look up any given RR type and retrieve an
example via the common host lookup tools:

```
host -t a a.dns.netmeister.org
dig aaaa aaaa.dns.netmeister.org +short
nslookup -query=cname cname.dns.netmeister.org
...
```

Since this zone is DNSSEC signed and uses NSEC instead
of NSEC3, you can easily walk the entire zone.

Note: not all of the values (RDATA) of these RRs
necessarily is meaningful, correct, or make sense.
They are, however, valid.

Your client may not support all RRs.  If you do not
get a response (or not the response you expected), try
performing an ANY lookup against
`panix.netmeister.org`.

A longer discussion of each record an be found at:
[https://www.netmeister.org/blog/dns-rrs.html](https://www.netmeister.org/blog/dns-rrs.html)
