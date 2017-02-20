
# Main Reclass Inventory #

<!-- -meta- trivial -->
This reclass[1] inventory is intended to be used from the maestro.sh[2]
script.

<!-- -meta- trivial -->
It consists of two subdirectories 'nodes' and 'classes'. For details,
please visit the reclass[1] documentation, only the very basics
are covered here.

<!-- -meta- basic -->
A class is a yaml file that bundles information which can be used by
certain nodes/hosts.
This is sometimes also called 'a group'.
The classes constitute the branches of the inventory tree.

<!-- -meta- detail -->
Classes
can reference each other and are searched deeply, in the order of
appearance and only once. The more common value is overwritten by the
more specific, lists and maps are expanded.

<!-- -meta- basic -->
Nodes are the leafes of the inventory tree, and reference the classes
mentioned above. The nodes (aka 'hosts') are organized in projects.

<!-- -meta- detail -->
A project is simply
a subdirectory of 'nodes' and usually has an associated class
('classes/project/{project-name}.yml') that is referenced by all its hosts.

<!-- -meta- trivial -->
For further details of nodes, classes, or their elements, please also see
the README file inside the respective directory or subdirectory.

----

 [1] http://reclass.pantsfullofunix.net/

 [2] https://github.com/zwischenloesung/common-playbooks

