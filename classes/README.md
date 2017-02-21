## Reclass Classes ##

<!-- -meta- basic -->
The classes in this directory are bundled in the following groups (subdirectories)
and should usually be applied in this order (unless you know what you
are doing, of course):
* admin - infos about human agents
* os - os and distro
* host - information about how a certain node is hosted
* location - physical location info
* project - main classes to organize the nodes
* manager - how a node is managed and by whom
* app - bundles info of a certain application
* service - more concrete services for the roles above
* role - data collection of how a node is expected to behave

<!-- -meta- detail-->
To get started, you can use the following rules of thumb.
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

<!-- -meta- basic -->
Note: Whenever it is quite clear that a certain parameter can be
associated with a certain class, please try namespacing it accordingly.
I.e. every subdirectory is added to the parameter name, the directory
names are separated by "\_\_" (e.g. ansible does not support other
special characters than underlines). Alternatively you can use maps
of the same name as the class.

