## Reclass Classes ##

<!-- -meta- basic -->
The classes in this directory are bundled in the following groups (subdirectories)
and should usually be applied in this order (unless you know what you
are doing, of course):
* admin - infos about human agents
* host - information about how a certain node is hosted
* project - main classes to organize the nodes
* os - os and distro
* location - physical location info
* manager - how a node is managed and by whom
* role - data collection of how a node is expected to behave
* service - more concrete services for the roles above
* app - bundles info of a certain application

<!-- -meta- basic -->
Note: Whenever it is quite clear that a certain parameter can be
associated with a certain class, please try namespacing it accordingly.
I.e. every subdirectory is added to the parameter name, the directory
names are separated by "\_\_" (e.g. ansible does not support other
special characters than underlines). Alternatively you can use maps
of the same name as the class.

