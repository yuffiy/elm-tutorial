# Messages

In the last section, we created an application using Html.App that was just static Html. Now let's create an application that responds to user interaction using messages.

```elm
module Main exposing (..)

import Html exposing (Html, button, div, text)
import Html.Events exposing (onClick)
import Html.App


-- MODEL


type alias Model =
    Bool


init : ( Model, Cmd Msg )
init =
    ( False, Cmd.none )



-- MESSAGES


type Msg
    = Expand
    | Collapse



-- VIEW


view : Model -> Html Msg
view model =
    if model then
        div []
            [ button [ onClick Collapse ] [ text "Collapse" ]
            , text "Widget"
            ]
    else
        div []
            [ button [ onClick Expand ] [ text "Expand" ] ]



-- UPDATE


update : Msg -> Model -> ( Model, Cmd Msg )
update msg model =
    case msg of
        Expand ->
            ( True, Cmd.none )

        Collapse ->
            ( False, Cmd.none )



-- SUBSCRIPTIONS


subscriptions : Model -> Sub Msg
subscriptions model =
    Sub.none



-- MAIN


main =
    Html.App.program
        { init = init
        , view = view
        , update = update
        , subscriptions = subscriptions
        }
```

This program is very similar to the previous program we did, but now we have two messages: `Expand` and `Collapse`. You can run this program by copying it into a file and opening it using Elm reactor. 

Let's look more closely at the `view` and `update` functions.

### View

```elm
view : Model -> Html Msg
view model =
    if model then
        div []
            [ button [ onClick Collapse ] [ text "Collapse" ]
            , text "Widget"
            ]
    else
        div []
            [ button [ onClick Expand ] [ text "Expand" ] ]
```

Depending on the state of the model we show either the collapsed or the expanded view. 

Note the `onClick` function. As this view is of type `Html Msg` we can trigger messages of that type using `onClick`. Collapse and Expand are both of type Msg.

### Update

```elm
update : Msg -> Model -> ( Model, Cmd Msg )
update msg model =
    case msg of
        Expand ->
            ( True, Cmd.none )

        Collapse ->
            ( False, Cmd.none )
```

`update` responds to the possible messages. Depending on the message, it returns the desired state. When the message is `Expand`, the new state will be `True` (expanded). 

Next let's see how __Html.App__ orchestrates these pieces together.
