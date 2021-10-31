# Provably-lost-and-found
An experiment in systems that allow the the owner to lose a digital object within a digital space. Where that object can only be found by visiting that space. 

1. A _creator_ generates a digital _artefact_ (e.g. an NFT)
2. The _creator_ generates a _distributionProfile_ across a shared _digitaSpace_
3. The _creator_ presents the _distributionProfile_ and _digitaSpace_ to a _obfiscator_ that hides the _artefact_.
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
