# Ejercicio 0.4: Nuevo diagrama de nota

Ejercicio 0.4 donde se establece un diagrama donde se muestre el comportamiento del navegador y el servidor cuando
el usuario envía una nota a través de la app de Notas.

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

    Note left of server: El servidor regresa el formulario HTML

    browser->>server: HTTP GET <https://studies.cs.helsinki.fi/exampleapp/main.css>
    activate server
    server-->>browser: the css file
    deactivate server

    Note left of server: El servidor regresa el archivo CSS

    browser->>server: HTTP GET <https://studies.cs.helsinki.fi/exampleapp/main.js>
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    Note left of server: El servidor regresa el archivo JavaScript

    browser->>server: HTTP GET <https://studies.cs.helsinki.fi/exampleapp/main.js>
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    Note right of browser: El browser ejecuta el JS para obtener el JSON de las notas del lado del servidor


    browser->>server: HTTP GET <https://studies.cs.helsinki.fi/exampleapp/data.json>
    activate server
    server-->>browser: [{ "content": "dfg", "date": "2024-08-02" }, ... ]
    deactivate server

    Note right of browser: The browser ejecuta el JS y se renderiza en el HTML para mostrar las notas


```


# Ejercicio 0.5: Diagrama de aplicación de una sola página

Ejercicio 0.5 donde se establece un diagrama donde se muestre el comportamiento del navegador y el servidor cuando
el usuario abre la app de una sola página, que en mi opinión no camia en nada del anterior ejercicio.

```mermaid

sequenceDiagram
    participant browser
    participant server

    browser->>server: HTTP GET <https://studies.cs.helsinki.fi/exampleapp/spa>
    activate server
    server-->>browser: HTML document
    deactivate server

    Note left of server: El servidor regresa el formulario HTML

    browser->>server: HTTP GET <https://studies.cs.helsinki.fi/exampleapp/main.css>
    activate server
    server-->>browser: the css file
    deactivate server

    Note left of server: El servidor regresa el archivo CSS

    browser->>server: HTTP GET <https://studies.cs.helsinki.fi/exampleapp/spa.js>
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    Note left of server: El servidor regresa el archivo JavaScript

    browser->>server: HTTP GET <https://studies.cs.helsinki.fi/exampleapp/data.json>
    activate server
    server-->>browser: [{ "content": "dfg", "date": "2024-08-02" }, ... ]
    deactivate server

    Note right of browser: The browser ejecuta el JS y se renderiza en el HTML para mostrar las notas


```

# Ejercicio 0.6: Nueva nota en diagrama de aplicación de una sola pagina

Ejercicio 0.6 donde se establece un diagrama donde se muestre el comportamiento del navegador y el servidor cuando
el usuario inserta una nueva nota, aqui según el seguimiento por Network solo se envía.

```mermaid

sequenceDiagram
    participant browser
    participant server

    Note right of browser: El browser ejecuta solo el JS desde el input y obtiene el JSON de las notas del lado del servidor

    browser->>server: HTTP POST <https://studies.cs.helsinki.fi/exampleapp/new_note_spa>
    activate server
    server-->>browser: [{ "content": "dfg", "date": "2024-08-02" }, ... ]
    deactivate server

    Note right of browser: The browser ejecuta el JS y renderiza el HTML para agregar la nueva notas


```


