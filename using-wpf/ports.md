[title]: # (Ports)
[tags]: # (WPF)
[priority]: # (11)
# Port Numbers

Default ports (as defined by the browser) are stripped by the browser and treat URLs the same, this means basically that `http://someurl` is the same as `http://someurl:80` and `https://someurl`.

When the domain is a non-primary / secondary domain, the port becomes part of the unique identifier and will be recorded independently.

* 10.0.0.61:55 is not the same as 10.0.0.61:555 or 10.0.0.61
* blue.local.something is not the same as blue.local.something:8080
