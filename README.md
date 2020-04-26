# Cardinal System

A Sword Art Online (SAO) inspired mmo engine. This is the theoritical / changelog part of the project to track progress and docuement infrastructure.

# Design

The engine is made from **Nodes** each node can be of different type, some are just there to relay data and others are just there to compute data and manage data. 

Depending on node type they will have access to various common classes to let them interact with data. A Circuit node whos goal is to relay data does not need to be able to access player or item classes to know what it is transporting. A Yui node whos goal is to monitor and view data and analyze discepenties should be able to read all.

Some nodes should be tied to the system but only temporary ran. For instance the ques creator node will work in cron manner go online get recent news and data and dynamically compute quests from recent data then push it to the database and go back offline. These can be classified as research node.

# Nodes

Various node types handle various tasks.

- Circuits: Their goal is to simply relay data from one node to another.  Each node adjacent to another should be connected to a Circuit Node.

- Yui: Inpires by this represents a node that can monitor the health of other nodes. It can interface and read all information from each node and compute it. However it can't modify or change the data.

- Ruru: In sao puts boss to sleep. Ideal node that is used for migrating and cloning existing noded (migrating data)

- Library: Data storing / Managing (sql backup)

- Heathcliff: Admin interface, manage and modify network.

- Monument: Similar to the monument of life in SAO those nodes goal is to log info

- Memory: Handling real time data, should have a priority link to Library to backup live data.

- Seed: A node that creates the server instance with configuration. It constantly watches configuration file changes and pushes new nodes.

- Achievement: Node that handles all achievements.

- Server: Basic game engine should be able to have one server per floor / area to release load.

- Unassigned: A node standing by 



Entity principle, for instance a player entity while process running should have: `RegisterInterest`, `RegisterOwner`, `CurrentOwner`, `EntityOwnerSwap`

## Current Progress

- [x] Nodes

- [ ] Entities

- [x] Nodes --> Circuits

- [ ] Nodes --> Yui

- [ ] Nodes --> Ruru

- [ ] Nodes --> Library

- [ ] Nodes --> Heathcliff

- [ ] Nodes --> Monument

- [ ] Noded --> Memory

- [x] Nodes --> Seed

- [x] Nodes --> Achievement

- [ ] Nodes --> Server

- [x] Nodes --> Unassigned
