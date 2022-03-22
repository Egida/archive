**A custom repo for Cloudflare firewall ruleset currently in use at https://cyber-hub.pw/ https://cyber-hub.net/  **
```
1 => T1 "Country" (aka TOR) is always challenged to avoid TOR routed HTTP floods.
2 => A good set of known hosting/VPN ASN to be challenged in order to avoid proxy based HTTP floods.
3 => Consider setting your site with "Under Attack Mode" (UAM) to enable a JS challenge to all IPs.
```


**Additional mitigations can be applied as:**


```
1 => Nginx (or webserver/balancer) rate limit closing/resetting the connections (Nginx ex: error code 444) triggering the Cloudflare "Origin protection" and "HTTP DDoS attack protection".
2 => Monitoring of HTTP requests in order to detect spikes and forcing a captcha challenge for any ASN
3 => Block of unwanted HTTP methods via Cloudflare firewall rules
4 => Block of URI queries via Cloudflare firewall rules when sites does not require it in order to avoid cache bypass (ex. static site parts, pretty urls)
5 => Block invalid user agents with a rule like:
(http.user_agent eq "a") or (http.user_agent eq "b") or (http.user_agent eq "c") or (http.user_agent eq "d") or (http.user_agent eq "e") or (http.user_agent eq "f") or (http.user_agent eq "g") or (http.user_agent eq "h") or (http.user_agent eq "i") or (http.user_agent eq "j") or (http.user_agent eq "k") or (http.user_agent eq "l") or (http.user_agent eq "m") or (http.user_agent eq "n") or (http.user_agent eq "o") or (http.user_agent eq "p") or (http.user_agent eq "q") or (http.user_agent eq "r") or (http.user_agent eq "s") or (http.user_agent eq "t") or (http.user_agent eq "u") or (http.user_agent eq "v") or (http.user_agent eq "w") or (http.user_agent eq "x") or (http.user_agent eq "y") or (http.user_agent eq "z") or (http.user_agent eq "A") or (http.user_agent eq "B") or (http.user_agent eq "C") or (http.user_agent eq "D") or (http.user_agent eq "E") or (http.user_agent eq "F") or (http.user_agent eq "G") or (http.user_agent eq "H") or (http.user_agent eq "I") or (http.user_agent eq "J") or (http.user_agent eq "K") or (http.user_agent eq "L") or (http.user_agent eq "M") or (http.user_agent eq "N") or (http.user_agent eq "O") or (http.user_agent eq "P") or (http.user_agent eq "Q") or (http.user_agent eq "R") or (http.user_agent eq "S") or (http.user_agent eq "T") or (http.user_agent eq "U") or (http.user_agent eq "V") or (http.user_agent eq "W") or (http.user_agent eq "X") or (http.user_agent eq "Y") or (http.user_agent eq "Z") or (http.user_agent eq "1") or (http.user_agent eq "2") or (http.user_agent eq "3") or (http.user_agent eq "4") or (http.user_agent eq "5") or (http.user_agent eq "6") or (http.user_agent eq "7") or (http.user_agent eq "8") or (http.user_agent eq "9") or (http.user_agent eq "0") or (http.user_agent eq "~") or (http.user_agent eq "`") or (http.user_agent eq "!") or (http.user_agent eq "@") or (http.user_agent eq "#") or (http.user_agent eq "$") or (http.user_agent eq "%") or (http.user_agent eq "^") or (http.user_agent eq "&") or (http.user_agent eq "*") or (http.user_agent eq "(") or (http.user_agent eq ")") or (http.user_agent eq "-") or (http.user_agent eq "_") or (http.user_agent eq "+") or (http.user_agent eq "=") or (http.user_agent eq "[") or (http.user_agent eq "]") or (http.user_agent eq "{") or (http.user_agent eq "}") or (http.user_agent eq ";") or (http.user_agent eq "'") or (http.user_agent eq "\\") or (http.user_agent eq ":") or (http.user_agent eq "\"") or (http.user_agent eq "|") or (http.user_agent eq ",") or (http.user_agent eq ".") or (http.user_agent eq "/") or (http.user_agent eq "<") or (http.user_agent eq ">") or (http.user_agent eq "?") or (http.user_agent eq "")
```

Stay safe :D

