
find a Debian or Ubuntu box with root on a clean public IP and run:

    apt-get update\
	  && apt-get -y install vim dnsutils curl sudo\
	  && curl -fsSL https://get.docker.com/ | sh || apt-get -y install docker.io\
	  && mkdir -p ~/netflix-proxy\
	  && cd ~/netflix-proxy\
	  && curl -fsSL https://github.com/steamsv/netflix-proxy/archive/latest.tar.gz | gunzip - | tar x --strip-components=1\
	  && ./build.sh

See the [**Wiki**](https://github.com/steamsv/netflix-proxy/wiki) page(s) for some common troubleshooting ideas.

<a href="https://dashboard.unzoner.com/sub"><img align="left" src="https://api.unzoner.com/api/v1.0/countries/available/flags.png"></a><br><br>

# about
`netflix-proxy` is a smart DNS proxy to stream `Netflix`, `Hulu`[[n2]](#footnotes), `HBO Now` and others out of region. It is deployed using Docker containers and uses `dnsmasq`[[n18]](#footnotes) and `sniproxy`[[n1]](#footnotes) to provide SmartDNS services. It works for some blocked sites, such as [PornHub](http://www.pornhub.com/) and [YouTube](https://en.wikipedia.org/wiki/Blocking_of_YouTube_videos_in_Germany). [Subscribe](http://eepurl.com/cb4rUv) to the mailing list and be notified of new features, updates, etc.

# supported services
The following are supported out of the box, however adding additional services is trivial and is done by updating `dnsmasq.conf` file and running `docker restart dnsmasq`:
* Netflix
* Hulu[[n2]](#footnotes)
* HBO Now
* Amazon Instant Video
* Crackle
* Pandora
* Vudu
* blinkbox
* BBC iPlayer[[n5]](#footnotes)
* NBC Sports and potentially many [more](https://github.com/ab77/netflix-proxy/blob/master/proxy-domains.txt)
