# exerc_hels_0



```mermaid

sequenceDiagram
    participant browser
    participant server

    browser->>server: HTTP POST <https://studies.cs.helsinki.fi/exampleapp/new_note>
    activate server
    server-->>browser: Response HTTP 302
    deactivate server

    Note right of browser: El browser envia al servidor envia la entrada del usuario y contesta con una redireccion

    browser->>server: HTTP GET <https://studies.cs.helsinki.fi/exampleapp/notes>
    activate server
    server-->>browser: HTML document
    deactivate server

    Note right of browser: El servidor regresa el formulario HTML

    browser->>server: HTTP GET <https://studies.cs.helsinki.fi/exampleapp/main.css>
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: HTTP GET <https://studies.cs.helsinki.fi/exampleapp/main.js>
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    browser->>server: HTTP GET <https://studies.cs.helsinki.fi/exampleapp/main.js>
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    Note left of browser: El browser ejecuta el JS para obtener el JSON de las notas del lado del servidor
    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: HTTP GET <https://studies.cs.helsinki.fi/exampleapp/data.json>
    activate server
    server-->>browser: [{ "content": "dfg", "date": "2024-08-02" }, ... ]
    deactivate server

    Note right of browser: The browser ejecuta el JS y se renderiza en el HTML para mostrar las notas
    Note right of browser: The browser executes the callback function that renders the notes


```
