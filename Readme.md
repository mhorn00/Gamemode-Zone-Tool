# Gamemode Zone Tool S&Box Systems
## Tool gun
* The toolgun itself
    * Zone placement
        * Place corners of zone for 'big picture' quick placement
        * Snapping to other zones
        * Fine size adjustment
            * Grab corner of zone, move in one or all axes
            * Grab edge of zone, move in one or all axes
            * Grab center of zone, move in one or all axes
* GUI Components
    * Text/C# editor (if hotloading is supported)
        * Code highlighting etc, can probably be taken from existing implementations
    * Zone Property editor
    * Template editor
    * Zone overview
        * List of every zone
        * Teleport to zone button
        * Open zone property editor
        * Search / filters (i.e. based off distance to player, certain templates)
## Serverside Zone System
* Serverside storage of zone
* RPC to update and request zones
    * Zone Placed
    * Zone Updated (arbitrary properties)
    * Zone Removed
## Zone Loader from external sources (addons or player definition)
* Global zone registry
    * Import register function in custom zones, templates and add them to global registry
* loading from other addons
    * Use registration system
* loading from maps
    * TBD, depends on what can and can't be loaded in S&Box
    * TBD, depends on what can and can't be loaded in S&Box
## Zone entity
* Templates
    * Gamemode, map or player defined default event implementations, non-internal properties (i.e. coordinates should not be templated)
    * Subtemplating
* Required properties
    * Worldspace coordinates
    * Width, height, depth
    * Yaw, pitch, roll
    * UUID (auto-generate)
    * Loaded by (gamemode, map, or player)
* Optional Properties
    * Color
    * Texture
    * Rendering properties (i.e. cast shadow, translucent, etc)
    * Display Name
* Custom properties
    * Arbitrary key value pair accessible programatically
    * Const properties
* Internal collision handlers to call API bound events
    * Rigidbody/physics object on the zone to process and call events
## Zone API Events (examples currently, not exhaustive)
* onCollision
* onPlayerEnter
* onPlayerExit
* onDamage