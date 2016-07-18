# The Players resource

We will organise our application structure by the name of the resources in our application. In this app, we only have one resource (`Players`) so there will be only a `Players` directory.

The `Players` directory will have modules just like the main level, one module per component of the Elm architecture:

- Players/Messages.elm
- Players/Models.elm
- Players/Update.elm

However, we will have different views for players: A list and a edit view. Each view will have its own Elm module:

- Players/List.elm
- Players/Edit.elm

