
# Single Page App Sequence Diagram

sequenceDiagram
    participant browser
    participant server
    Note right of browser: User navigates to the SPA at /spa
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: HTML document
    deactivate server
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: CSS file
    deactivate server
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server
    server-->>browser: JavaScript file (SPA logic)
    deactivate server
    Note right of browser: Page loads - existing notes rendered locally
    Note right of browser: User enters a note and clicks "Save" button
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa (JSON data)
    activate server
    server-->>browser: HTTP 201 Created
    deactivate server
    Note right of browser: New note appears instantly without a page reload
