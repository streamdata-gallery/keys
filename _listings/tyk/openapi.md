swagger: "2.0"
x-collection-name: Tyk
x-complete: 1
info:
  title: Tyk Gateway REST API
  description: the-api-for-managing-the-tyk-api-management-gateway-allowing-api-control-over-the-operation-of-a-variety-of-apis-
  termsOfService: https://tyk.io/terms-and-conditions/
  version: "1.9"
host: '{baseURL}'
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /tyk/keys/:
    get:
      summary: Get Keys
      description: Gets a list of *key* IDs (will only work with non-hashed installations)
      operationId: gets-a-list-of-key-ids-will-only-work-with-nonhashed-installations
      x-api-path-slug: tykkeys-get
      parameters:
      - in: query
        name: api_id
        description: Back-end to target
      - in: header
        name: x-tyk-authorization
        description: tyk gateway shared secret
      responses:
        200:
          description: OK
      tags:
      - API Key
  /tyk/keys/create:
    post:
      summary: Create Key
      description: Create a new *API token* with the *session object* defined in the
        body
      operationId: create-a-new-api-token-with-the-session-object-defined-in-the-body
      x-api-path-slug: tykkeyscreate-post
      parameters:
      - in: body
        name: session_object
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: suppress_reset
        description: Adding the `suppress_reset` parameter and setting it to `1`,
          will cause Tyk to not reset the quota limit that is in the current live
          quota manager
      - in: header
        name: x-tyk-authorization
        description: tyk gateway shared secret
      responses:
        200:
          description: OK
      tags:
      - API Key
  /tyk/keys/{keyId}:
    put:
      summary: Update Key
      description: Update an *API token* with the *session object* defined in the
        body, this operatin overwrites the existing object
      operationId: update-an-api-token-with-the-session-object-defined-in-the-body-this-operatin-overwrites-the-existin
      x-api-path-slug: tykkeyskeyid-put
      parameters:
      - in: query
        name: api_id
        description: Back-end to target
      - in: path
        name: keyId
        description: Access Token
      - in: body
        name: session_object
        schema:
          $ref: '#/definitions/holder'
      - in: query
        name: suppress_reset
        description: Adding the `suppress_reset` parameter and setting it to `1`,
          will cause Tyk to not reset the quota limit that is in the current live
          quota manager
      - in: header
        name: x-tyk-authorization
        description: tyk gateway shared secret
      responses:
        200:
          description: OK
      tags:
      - API Key
    post:
      summary: Add Custom Key
      description: Add a pre-specified *API token* with the *session object* defined
        in the body, this operatin creates a custom token that dsoes not use the gateway
        naming convention for tokens
      operationId: add-a-prespecified-api-token-with-the-session-object-defined-in-the-body-this-operatin-creates-a-cus
      x-api-path-slug: tykkeyskeyid-post
      parameters:
      - in: path
        name: keyId
        description: Access Token
      - in: body
        name: session_object
        schema:
          $ref: '#/definitions/holder'
      - in: header
        name: x-tyk-authorization
        description: tyk gateway shared secret
      responses:
        200:
          description: OK
      tags:
      - API Key
    delete:
      summary: Remove Key
      description: Remove this *API token* from the gateway, this will completely
        destroy the token and metadata associated with the token and instantly stop
        access from being granted
      operationId: remove-this-api-token-from-the-gateway-this-will-completely-destroy-the-token-and-metadata-associate
      x-api-path-slug: tykkeyskeyid-delete
      parameters:
      - in: query
        name: api_id
        description: Back-end to target
      - in: path
        name: keyId
        description: Access Token
      - in: header
        name: x-tyk-authorization
        description: tyk gateway shared secret
      responses:
        200:
          description: OK
      tags:
      - API Key