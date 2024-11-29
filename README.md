# TP Containers

*The specified script is used as a storage system for our scripts such as Warehouses, Motels, Housing, Player Stores, by supporting multiple frameworks at the same time.  Other developers are also able to use it by using our Events and Exports for creating, registering and opening containers very easy.*

## Events

### Register custom container.

- `@parameter (text) name` : Is the required name to set for this custom container (such as: Motel Room #1)
- `@parameter (number) weight` : Is the required total / maximum weight of the container (that can carry).
- `@parameter (true / false) create` : Is the required type for creating (inserting) into the sql the registered custom container or not. This parameter is for safety reasons, the specified event should only be called once to register this custom container and not multiple times (create parameter should be true).

```lua
TriggerEvent("tp_containers:server:registerCustomContainer", name, weight, create) -- Server side to server side.
TriggerServerEvent("tp_containers:server:registerCustomContainer", name, weight, create) -- Client side to server side.
```

### Upgrade custom container weight

- `@parameter (number) containerId` : Is the required custom container ID which is located on `tp_containers` sql table.
- `@parameter (number) extraWeight` : Is the required for adding extra weight to an existing custom container (upgrading / increasing its weight).

```lua
TriggerEvent("tp_containers:server:upgradeContainerInventoryWeight", containerId, extraWeight) -- Server side to server side.
TriggerServerEvent("tp_containers:server:upgradeContainerInventoryWeight", containerId, extraWeight) -- Client side to server side.
```

### Open custom container by its ID

**You are allowed to edit the specified event since we provide it public, mostly for safety reasons.**

- `@parameter (number) containerId` : Is the required custom container ID which is located on `tp_containers` sql table.

```lua
TriggerClientEvent("tp_containers:client:openInventoryContainerById", source, containerId) -- Server side to client side.
TriggerEvent("tp_containers:server:registerCustomContainer", containerId) -- Client side to client side.
```

## Exports

### Open custom container by its ID

- `@parameter (number) containerId` : Is the required custom container ID which is located on `tp_containers` sql table.

```lua
exports.tp_containers:OpenInventoryContainerById(containerId)
```
