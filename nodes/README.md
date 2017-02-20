
# Collection of Nodes #

<!-- -meta- trivial -->
This directory contains the nodes/hosts, seperated by project.
A project directory
basically is only a namespace to make clear what belongs together.

<!-- -meta- basic -->
What belongs together, i.e. what constitutes a project,
is decided primarily on the common reference of the
same classes. Therefore a group of classes was introduced that contains a
member for every project, such that every node of a project can
reference that class to get the infos common to all members 
('classes/project/{project-name}.yml').

<!-- -meta- detail -->
It might be a good idea to define projects also based on accounting
considerations, such that future splitting of the repository is
less complex - e.g. use a seperate project per customer or foundation.

<!-- -meta- detail -->
For the later splitting, one only has to make sure that all the referenced
classes are available.

<!-- -meta- basic -->
Something similar was introduced for the nodes themselves. There is a group
of classes that match hostnames ('classes/host/{hostname}.yml'). It is
used to store the information like the hosts hardware resources or location,
things that might be relevant without (or prior to the creation of) the
actual host, and could be shared with other nodes. Of course, a generalization
can be used also here: if you have a cluster of nodes that really are the
same except, let's say, for hostname and ip, just one host class can hold
that information, the hostname and the ip are then filled up by the
configuration management engine via a range for example.

<!-- -meta- detail -->
Every such class is thought to be referenced
first of all, by the corresponding host itself. It yet serves another purpose
too: a virtualization host references all its client hosts, as it needs to
know the resources to provide it with. But also for the client machine one
might want to know its hypervisor, so a special class called
host.Host\_{hostname} was introduced, which is only to be referenced by
the clients (and not by that hypervisor itself).

<!-- -meta- detail -->
Note: Always reference first the other hosts and only then the host
in question to make sure the current host will have set its parameters
last in order to overwrite other values.

## Order of Classes in Nodes ##

<!-- -meta- basic -->
As classes are parsed in the order appearing - remember the rule is depth
search, process only once - a class that uses the parameters of another
class must come after that class. Usually the following order should work:

 * start with the `os` as this is straightforward
 * followed by the `host` as this is host specific and should not contain
   too much information that can be shared
 * then use the `project` class, as this will trigger the switch for the
   little more sharable infos
 * the class `app` should be independent of everything else and just contain
   app related stuff. It is a good idea to reference `app` classes early.
 * classes in `services` typically reference the `app` classes.
 * finally the variables in the `role` classes can be set using the
   ones from apps and services in combination with the variables from
   hosts/projects
 
