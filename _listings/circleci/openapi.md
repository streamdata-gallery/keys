swagger: "2.0"
x-collection-name: CircleCI
x-complete: 1
info:
  title: CircleCI
  description: the-circleci-api-is-a-restful-fullyfeatured-api-that-allows-you-to-do-almost-anything-in-circleci--you-can-access-all-information-and-trigger-all-actions--the-only-thing-we-dont-provide-access-to-is-billing-functions-which-must-be-done-from-the-circleci-web-ui-
  version: 1.0.0
host: circleci.com
basePath: /api/v1
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /project/{username}/{project}/checkout-key:
    get:
      summary: Get Project Username Project Checkout Key
      description: Get project username project checkout key.
      operationId: getProjectUsernameProjectCheckoutKey
      x-api-path-slug: projectusernameprojectcheckoutkey-get
      responses:
        200:
          description: OK
      tags:
      - Project
      - Username
      - Project
      - Checkout
      - Key
    parameters:
      summary: Parameters Project Username Project Checkout Key
      description: Parameters project username project checkout key.
      operationId: parametersProjectUsernameProjectCheckoutKey
      x-api-path-slug: projectusernameprojectcheckoutkey-parameters
      responses:
        200:
          description: OK
      tags:
      - Parameters
      - Project
      - Username
      - Project
      - Checkout
      - Key
    post:
      summary: Add Project Username Project Checkout Key
      description: |-
        Creates a new checkout key.
        Only usable with a user API token.
      operationId: postProjectUsernameProjectCheckoutKey
      x-api-path-slug: projectusernameprojectcheckoutkey-post
      parameters:
      - in: body
        name: type
        description: The type of key to create
        schema:
          $ref: '#/definitions/holder'
      responses:
        200:
          description: OK
      tags:
      - Project
      - Username
      - Project
      - Checkout
      - Key
  /project/{username}/{project}/checkout-key/{fingerprint}:
    delete:
      summary: Delete Project Username Project Checkout Key Fingerprint
      description: Delete project username project checkout key fingerprint.
      operationId: deleteProjectUsernameProjectCheckoutKeyFingerprint
      x-api-path-slug: projectusernameprojectcheckoutkeyfingerprint-delete
      responses:
        200:
          description: OK
      tags:
      - Project
      - Username
      - Project
      - Checkout
      - Key
      - Fingerprint
    get:
      summary: Get Project Username Project Checkout Key Fingerprint
      description: Get project username project checkout key fingerprint.
      operationId: getProjectUsernameProjectCheckoutKeyFingerprint
      x-api-path-slug: projectusernameprojectcheckoutkeyfingerprint-get
      responses:
        200:
          description: OK
      tags:
      - Project
      - Username
      - Project
      - Checkout
      - Key
      - Fingerprint
    parameters:
      summary: Parameters Project Username Project Checkout Key Fingerprint
      description: Parameters project username project checkout key fingerprint.
      operationId: parametersProjectUsernameProjectCheckoutKeyFingerprint
      x-api-path-slug: projectusernameprojectcheckoutkeyfingerprint-parameters
      responses:
        200:
          description: OK
      tags:
      - Parameters
      - Project
      - Username
      - Project
      - Checkout
      - Key
      - Fingerprint
  /project/{username}/{project}/ssh-key:
    parameters:
      summary: Parameters Project Username Project Ssh Key
      description: Parameters project username project ssh key.
      operationId: parametersProjectUsernameProjectSshKey
      x-api-path-slug: projectusernameprojectsshkey-parameters
      responses:
        200:
          description: OK
      tags:
      - Parameters
      - Project
      - Username
      - Project
      - Ssh
      - Key
    post:
      summary: Add Project Username Project Ssh Key
      description: Create an ssh key used to access external systems that require
        SSH key-based authentication
      operationId: postProjectUsernameProjectSshKey
      x-api-path-slug: projectusernameprojectsshkey-post
      parameters:
      - in: body
        name: body
        schema:
          $ref: '#/definitions/holder'
      - in: header
        name: Content-Type
      responses:
        200:
          description: OK
      tags:
      - Project
      - Username
      - Project
      - Ssh
      - Key
  /user/heroku-key:
    post:
      summary: Add User Heroku Key
      description: Adds your Heroku API key to CircleCI, takes apikey as form param
        name.
      operationId: postUserHerokuKey
      x-api-path-slug: userherokukey-post
      responses:
        200:
          description: OK
      tags:
      - User
      - Heroku
      - Key