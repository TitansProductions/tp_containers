# TP Containers

*The specified script is used as a storage system for our scripts such as Warehouses, Motels, Housing, Player Stores, by supporting multiple frameworks at the same time.  Other developers are also able to use it by using our Events and Exports for creating, registering and opening containers very easy.*

## Events

### Register custom container.

```lua
TriggerEvent("tp_containers:server:registerCustomContainer", name, weight, create) -- Server side to server side.
TriggerServerEvent("tp_containers:server:registerCustomContainer", name, weight, create) -- Client side to server side.
```

### Open custom container by its ID

- You are allowed to edit the specified event since we provide it public, mostly for safety reasons.
- A container ID is located on `tp_containers` sql table.
```lua
TriggerClientEvent("tp_containers:client:openInventoryContainerById", source, containerId) -- Server side to client side.
TriggerEvent("tp_containers:server:registerCustomContainer", containerId) -- Client side to client side.
```

## Exports

### Open custom container by its ID
- A container ID is located on `tp_containers` sql table.
- 
```exports.tp_containers:OpenInventoryContainerById(containerId)```
