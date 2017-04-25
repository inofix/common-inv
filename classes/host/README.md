### Reclass Host Class ###

<!-- -meta- basic -->
As nodes always run on something, a description is needed to provide the
information how they are hosted.

<!-- -meta- detail -->
Every node has its own resource description in this directory. This information
can be used both by the host itself (node) and by its host (virtualization-host).

<!-- -meta- detail -->
The host should always first reference its guests and only then itself to make
sure the hosts propper info is overriding any info that might have been set by
some of its guests.

