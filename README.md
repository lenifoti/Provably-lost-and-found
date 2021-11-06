# Provably-lost-and-found
An experiment in systems that allow the the owner to lose a digital object within a digital space. Where that object can only be found by visiting a location within that space. 

1. A _creator_ generates a digital _artefact_ (e.g. an NFT)
2. The _creator_ generates a _distributionProfile_ across a shared _digitalSpace_
3. The _creator_ presents the _distributionProfile_ and _digitalSpace_ to a _obfiscator_ that hides the _artefact_.
4. The _creator_ assigns the discovery processto a _revealer_.
5. A _game_ defines the rules that constrain the locations available to _searchers_ at any point in time.
6. A  _Searcher_ submits a location to the _revealer_ that determines whether there is an item at that location.
7. The _revealer_ may give a private hint as to the location.
8. Once found, the _artefact_ is revealed to everyone, including any private hints.
9. A _searcher_ cannot cheat by following another, sharing information or conspiring.
10. _Serchers_ cannot randomly arrive at locations, they must supply proof of some form of progression.

An example game: Minesweeper where a successful player gets a prize proportional to the number of mines (relative to the number of squares).

Problems to be solved:
- Shared space: The space must be sharable. Items the have been revealed are know to all.
- Provably hidden: There is no way for any player or the creator to predict the location of an object without 'visiting' it.
- Sybil resistance: There is no way that a player can use multiple identities to improve their chances of finding a lost object.
- Bot resistance: There is no way that a program can gain advantage over a person
- Resistant to conspiracy: There is no way that 2 or more players can improve their chances by conspiring together.
- Concentrated distribution: There is a means of increasing the likelyhood of location of the object.

Creator -> _obfiscator_ "hide this _artefact_ in thie _digitalSpace_ using this _distributionProfile_".
Game -> _searcher_ "you have permission to search a location."
Searcher -> _revealer_ "is there an _artefact_ at this location." 

Reference: BitKong - a betting game where fruit are revealed.


IDEAS:
- proximity rule will reveal anything already known about the surrounding location
- random backoff timer for accepting for presenting to the blockchain
- re-trace check by presenting merkle proof of current location.
- probability ramp function for each player to prevent sybil attacks.

# An approach
**Losing an object.**
If something is truly lost, then no one knows where it is, not the owner of the space, the owner of the object or even the service that hides them.  When it is found it must be a surprise to everyone, because if it wasn't then it was not truely lost.
If no one can know where it is then it's location is of no consequence until it is found. Objects are then not hidden in a location, they are simply become locationless until a point in time when they will be discovered.

**Finding an object**
Under these assumptions, an object's location can be defined as a the location of a player at the 'point in time' that it is discovered. So to be lost, the 'point in time' and player must be concealed.  This is can be done with a true source of randomness, with the advantage that the occurence of truly random event cannot be known until it occurs, so there is no need for the object's location to be defined before the moment that it is found. 

**Relationships between players**
If we make the assumption that objects are also lost at an unknown time, then it is very possible for a second player to find an item after a location has been visited by another player.  In fact, it is possible for a player to find an object at a location tha they have previously visited.  The only information that needs to be shared between players is that an object has been found, in which case, its location should also be available to all players.

It would be somewhat unexpected for a player to discover an object on a second visit. However, it would not be unexpected for a player, who is not aware of the movements of other players, to find an object in a location that has been visited by other players.  For this reason, it is only necessary to exclude locations re-visited by a single player.

Not excluding locations visited by other players avoids the problem of players simply observing the movements of others. A player obviously knows where they have been so it makes sense to allow them to use this knowledge.

**Preventing automation**
Automation is a problem since an application can simply move across all locations really quickly. This is not fully effective because compressing time will actually reduce the probablility of finding things. However, it is still something that needs to be discouraged, because it will mean that a user can search the whole space, and only find a few of the items.  This could be explaiend by a) objects have not all be lost at that point in time, or b) the porbability of finding something is proportional to the speed at which one travels thorugh the space.
To discourage this, each location presented will emit an event informing the player of a time delay that they must wait before retrying.
Another method of defeating automation is to reject location updates above a certain speed (measured as a distance between locations over the time between updates).

**Preventing Sybil attacks**
Use of many identities is a more concerning problem, since it will increase the probability of finding objects.  This can be reduced by a rigorous enrolment process that uses or borrows from an app that includes proof of humanity.
Players can be permissioned before they submit, or they can simply be discouraged by ensuring that proof-of-humanity happens only once treasure has been found. Under this model, finding the object simply gives the player exclusive right to claim the object, however there is a time-limit after which unclaimed objects vanish.

**Location spoofing**
In a metaverse, moving around randomly is possible and can be discouraged by the speed test - it could even be limited to a single step in 4 or 8 directions.
In a global map (Pokemon Go style), the locations must be visited and locations can be spoofed.  The speed strategy works to some extent, but there are also many other tools that can be used. Cell-tower data and wifi access points can be cross referenced.

