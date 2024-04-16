 # Uniform Interface

Indicates that the server transfers informtion in a standard format

# Four Guiding principles of interface are:

1. Identification of Resources
2. Manipulation of Resources through these Representations
3. Self-Descriptive Messages
4. Hypermedia As The Engine Of Application State (HATEOAS)

# Identification of Resources

# Manipulation of Resources through these representations

# Self-Descriptive Messages

- Each Message includes enough information to describe how to process the message
    - For example: 
        - which parser to invoke may be specified by an internet mediatype ([MIME Type](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types/Common_types))
- Responses should also indicate their cache-ability
- Use  [Standard MIME Types](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types/Common_types) and RDF vocabulary to make a message self-descriptive

# Hypermedia as the engine of application state (AKA HATEOAS)

- Having accessed an initial URI for the REST application, a REST client should then be able to use server-provided links dynamically to discover all the avilable resources it needs
    - Meaning: As access proceeds -> the server responds with the text that includes hyperlinks to other resources that are currently available
- Clients:
    - Deliver State via: 
        - body contents
        - query-string parameters
        - request headers
        - the requested URI (The Resource Name)
- Services:
    - Deliver State to Clients via: 
        - Response Headers
        - Response Codes
        - Body Content
        - The necessary links are contained in the Body to supply the URI for retrieval of the object itself or related objects

### Sources

https://stackoverflow.com/questions/25172600/rest-what-exactly-is-meant-by-uniform-interface
http://en.wikipedia.org/wiki/Representational_state_transfer#Uniform_interface