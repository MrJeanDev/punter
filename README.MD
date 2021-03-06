# Punter

Punter (passive hunter) helps with the first step in footprinting a domain.  The idea is not to touch the target domain but passively find a good initial amount of information and put it into an easy to view report.  It uses:

* DNS Dumpster
* Whois
* Reverse whois on email
* Haveibeenpwned lookup on emails found
* CRT.sh to find subdomains
* Crimeflare to uncover true IP's behind Cloudflare

Whois and DNS lookups are still done on the host, not through an API, so if you are worried about that take precautions.  Otherwise, all other lookups are down using other services.

After the scan an HTML report is generated with results, just double click and open it.

## Setup

```
git clone https://github.com/nethunteros/punter
cd punter
pip install -r requirements.txt

```

### Setup - Arch Linux
```
su
git clone https://github.com/nethunteros/punter
cd punter
pip2 install -r requirements.txt
pip2 install ipaddr

python2 main.py -t google.com

```

## Run

If you want to enable Shodan when searching then you need to edit config.cfg.  Change enable to True then add your API key.

Change the target to domain you are interested in:

```python main.py -t google.com```

## Credits

* Everyone who built apis/websites this script scrapes form
* @jmingov for html fixes/putting up with my terrible scripts

## TODO: 

* Grab html of site/headers using another service
* Net range from Whois
* Better unicode fixes
* Try/except for all types of errors

## Test

This software is mainly tested under Kali Linux, we recommend use this distribution.
* Kali Linux, Python 2.7.13 - OK
* Arch Linux, Python 2.7.13 - OK
Currently Punter is [not supported under](not-supported.md)
