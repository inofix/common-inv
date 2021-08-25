### Reclass Host Class ###

<!-- -meta- basic -->
As nodes always run on something, a description is needed to provide the
information how they are hosted.

<!-- -meta- detail -->
Every node has its own resource description in this directory. This information
can be used both by the node itself and by its host (virtualization-host) - or
maybe even by some partner host (e.g. a router/firewall/load-balancer).

<!-- -meta- detail -->
The host should always first reference its guests and only then itself to make
sure the hosts propper info is overriding any info that might have been set by
some of its guests.

<!-- -meta- detail -->
It has proven to be quite useful to name the actual node starting with a
lowercase letter and with their fqdn in reverse order, e.g.
"testhost.example.net" becomes "net\_example\_testhost.yml". On the
other hand the node's host or it's type can be summarized in files
starting with a captial letter, e.g. "Host\_net\_example\_kvmhost42.yml"
or "Virtual.yml".

