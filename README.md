# No more ads, tracking and other virtual garbage
All blocklists are gathered from multiple, actively maintained sources and automatically updated, cleaned, optimized and moderated on a daily basis.

The main [domains.txt](domains.txt) and [hostnames.txt](hostnames.txt) are designed for usage with [dnsmasq](http://www.thekelleys.org.uk/dnsmasq/doc.html), but a [dnscrypt-proxy](https://github.com/DNSCrypt/dnscrypt-proxy) [combined blacklist](dnscrypt-proxy/dnscrypt-proxy.blacklist.txt) with the same coverage is also available as it has the added benifit of being able to [block](https://github.com/DNSCrypt/dnscrypt-proxy/issues/1067) [cnames](https://github.com/uBlockOrigin/uBlock-issues/issues/780). For any other adblocker that support the AdblockPlus format a [network filter](adblock/adblock.txt) list is available.

## General blocklist policies
 - Should not break useful websites or apps
 - Blocks tracking servers
 - Blocks advertising servers
 - Blocks analytics servers
 - Blocks scam websites
 - Blocks malware servers
 - Blocks webminers
 - Blocks phishing servers
 
## Optimization
The optimizer makes full use of domainname based wildcard filtering `*.doubleclick.net`, this reduces the chance of missing any new subdomains and significantly reduces the size of the blocklists. Hostnames that cannot be blocked on a domain level will still be listed in a regular hostname based blocklist.

## Dead hosts removal
All hostname DNS records are constantly monitored for updates. In case the A, AAAA, CNAME and NS records return NXDOMAIN they will be marked as dead and removed from hostnames.txt. Domains are tested on their whois data, all unregistered domains will be filtered out of domains.txt.

The current list of dead hostnames can be found [here](https://github.com/notracking/hosts-blocklists-scripts/blob/master/hostnames.dead.txt) and have a look [here](https://github.com/notracking/hosts-blocklists-scripts/blob/master/domains.dead.txt) for all unregistered domains.

## DNS over HTTPS (DOH)
DNS over HTTPS will prevent clients in your network from using the default local DNS services. Mozilla Firefox has a feature to disable DOH network wide for all clients as described [here](https://support.mozilla.org/en-US/kb/configuring-networks-disable-dns-over-https).

All domain and combined lists will block the canary domain `use-application-dns.net`, disabeling DOH by default on all clients.

# How to install
 - [Instructions for AdblockPlus](https://github.com/notracking/hosts-blocklists/wiki/Install-AdblockPlus) (eg. [uBlock](https://github.com/gorhill/uBlock), [Adguard Home](https://github.com/AdguardTeam/AdGuardHome/))
 - [Instructions for dnsmasq](https://github.com/notracking/hosts-blocklists/wiki/Install-dnsmasq)
 - [Instructions for dnscrypt-proxy](https://github.com/notracking/hosts-blocklists/wiki/Install-dnscrypt-proxy)
 - [Instructions for Pi-hole](https://github.com/notracking/hosts-blocklists/wiki/Install-pi-hole)

## Supporting Notracking blocklist
You can support in multiple ways:
 - Submit false positives
 - Submit new (tested) sources
 - [Donate with Paypal](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=VPTVYWY3B7XWG&source=url)

# Sources
Most sources come from public hostfile type lists, though several AdblockPlus lists are also included only for their non-3rd party networking filters `||evilhost.com^`. See [SOURCES.md](SOURCES.md) for the full overview of all included lists.
