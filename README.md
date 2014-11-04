dnsmasq-china-list
==================

Configuration for hot China domains (or CDN domains that have node in China) to accelerate via Dnsmasq (Now also includes bogus-nxdomain lines to stop common DNS servers from hijacking NXDOMAIN results)

Content
=======

- `accelerated-domains.china.conf`: Acceleratable Domains.

  The domain should have a better resolving speed or result when using a Chinese DNS server.

  To determine if a domain is eligible, one of the criteria below must be met:

 - The domain's NS server is located in China.

 - The domain will resolve to an IP located in China mainland when using a Chinese DNS server, but _not_ always do when using a foreign DNS server (For example, CDN accelerated sites that have node in China). This however does _not_ include those having node _near_ China mainland, like in Japan, Hong Kong, Taiwan, etc.
 
  Please don't add subdomains if the top domain is already in the list. This includes all .cn domains which are already matched by the `/cn/` rule.

- `bogus-nxdomain.china.conf`: Known addresses that are hijacking NXDOMAIN results returned by DNS servers.

Usage
=====

1. Place accelerated-domains.china.conf and bogus-nxdomain.china.conf under /etc/dnsmasq.d/ (Create the folder if it does not exist).
2. Uncomment "conf-dir=/etc/dnsmasq.d" in /etc/dnsmasq.conf
3. (Optional) Place dnsmasq-update-china-list into /usr/bin/

License
=======

This piece of configurations and scripts are licensed under WTFPL v2, below is the full text version:

               DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE
                       Version 2, December 2004
    
    Copyright (C) 2004 Sam Hocevar <sam@hocevar.net>
    
    Everyone is permitted to copy and distribute verbatim or modified
    copies of this license document, and changing it is allowed as long
    as the name is changed.
    
               DO WHAT THE FUCK YOU WANT TO PUBLIC LICENSE
      TERMS AND CONDITIONS FOR COPYING, DISTRIBUTION AND MODIFICATION
    
     0. You just DO WHAT THE FUCK YOU WANT TO.
