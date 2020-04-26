# Design Changes

## Seed Node

This node now handles reading a conf file and creating the architecture based on the conf file. 

Created nodes are passed to the server entity for handling.

If conf file updates changes should be sent to server eg: kill X node or Add new node.