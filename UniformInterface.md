 # Uniform Interface

Indicates that the server transfers information in a standard format

# Four Guiding principles of interface are:

1. Identification of Resources
2. Manipulation of Resources through these Representations
3. Self-Descriptive Messages
4. Hypermedia As The Engine Of Application State (HATEOAS)

# Identification of Resources

## restfulapi.net:

- "A resource is a conceptual mapping to a set of entities, not the entity that corresponds to the mapping at any particular point in time." --Roy Fielding’s dissertation

- "The interface must uniquely identify each resource involved in the interaction between the client and the server.
- "As the constraint name itself applies, you MUST decide APIs interface for resources inside the system which are exposed to API consumers and follow it religiously. A resource in the system should have only one logical URI, and that should provide a way to fetch related or additional data. It’s always better to synonymize a resource with a web page."

## wikipedia:

- "Individual resources are identified in requests, for example using URIs in web-based REST systems. The resources themselves are conceptually separate from the representations that are returned to the client. For example, the server may send data from its database as HTML, XML or JSON, none of which are the server's internal representation, and it is the same one resource regardless."

## rando on stackoverflow;

- "You use the URI (IRI) standard to identify a resource. In this case, a resource is a web document.


## tl:dr: 

- Follow the URI guidelines strictly to allow api consumers to interact easily

# Manipulation of Resources through these representations

## restfulapi.net:

- "The resources should have uniform representations in the server response. API consumers should use these representations to modify the resource state in the server."

- ex: When returning a collection resource, include only the most important information about that resource. This will keep the size of the response payload small, and so will improve the performance of the API. Opposite to collection URI, a single resource URI includes complete information about a particular device. It also includes a list of links to sub-resources and other supported operations. This will make your REST API HATEOAS driven.

## wikipedia:

- "When a client holds a representation of a resource, including any metadata attached, it has enough information to modify or delete the resource."


## tl:dr: 

- keep your resource representations consistent, and have them contain necessary information to act upon them

# Self-Descriptive Messages

- Each Message includes enough information to describe how to process the message
    - For example: 
        - which parser to invoke may be specified by an internet mediatype ([MIME Type](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types/Common_types))
- Responses should also indicate their cache-ability
- Use  Standard MIME Types and [RDF vocabulary](https://www.w3schools.com/xml/xml_rdf.asp#:~:text=RDF%20Example&text=xml%20version%3D%221.0%22%3F%3E,-%3Crdf%3ARDF&text=The%20first%20line%20of%20the,%2Dsyntax%2Dns%23%22.) to make a message self-descriptive

# Hypermedia as the engine of application state (AKA HATEOAS)

- Having accessed an initial URI for the REST application, a REST client should then be able to use server-provided links dynamically to discover all the avilable resources it needs
    - Meaning: As access proceeds -> the server responds with the text that includes hyperlinks to other resources that are currently available
- **Clients**:
    - Deliver State via: 
        - body contents
        - query-string parameters
        - request headers
        - the requested URI (The Resource Name)
- **Services**:
    - Deliver State to Clients via: 
        - Response Headers
        - Response Codes
        - Body Content
        - The necessary links are contained in the Body to supply the URI for retrieval of the object itself or related objects

### Sources

- https://stackoverflow.com/questions/25172600/rest-what-exactly-is-meant-by-uniform-interface
- http://en.wikipedia.org/wiki/Representational_state_transfer#Uniform_interface
- https://restfulapi.net/
- https://restfulapi.net/resource-naming/
- https://restfulapi.net/rest-api-design-tutorial-with-example/
- https://stackoverflow.com/questions/25172600/rest-what-exactly-is-meant-by-uniform-interface