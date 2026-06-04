sequenceDiagram
    participant browser
    participant server

    Note right of browser: The user enters the input and clicks Save

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    Note right of browser: JS automatically adds new notes to the array and redraws the screen (without waiting for the server).
    
    Note left of server: Server save new note (data.json)
    server-->>browser: HTML status code 201 created
    deactivate server

    Note right of browser: The browser does not do anything extra (does not reload the page, does not send any additional requests).
