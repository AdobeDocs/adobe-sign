Managing Webhooks and Subscriptions (Webhook APIs)
==================================================

On this page
------------

-  `Endpoints <#endpoints>`__
-  `POST /webhooks <#postwebhooks>`__ Creates a new webhook.
-  `GET /webhooks <#getwebhooks>`__ Retrieves webhooks for a user.
-  `GET /webhooks/{webhookId} <#getwebhookswebhookid>`__ Retrieves details of a webhook.
-  `PUT /webhooks/{webhookId} <#putwebhookswebhookid>`__ Modifies an existing webhook.
-  `PUT /webhooks/{webhookId}/state <#putwebhookswebhookidstate>`__ Modifies an existing webhook’s status(ACTIVE/INACTIVE).
-  `DELETE /webhooks/{webhookId} <#deletewebhookswebhookid>`__ Deletes a webhook.
-  `Standard error codes in every API request <#standarderrorcodesineveryapirequest>`__
-  `Standard headers in every API request <#standardheadersineveryapirequest>`__

Webhook APIs are the means by which your integration communicates with the Adobe Sign service about webhooks. Use the various API endpoints to create, delete, modify, and retrieve status information about your webhooks.

Endpoints
---------

Adobe Sign APIs include the following endpoints:

POST /webhooks
~~~~~~~~~~~~~~

.. raw:: html

   <table>

.. raw:: html

   <thead>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Entity

.. raw:: html

   </th>

.. raw:: html

   <th>

Value

.. raw:: html

   </th>

.. raw:: html

   </tr>

.. raw:: html

   </thead>

.. raw:: html

   <tbody>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Description

.. raw:: html

   </td>

.. raw:: html

   <td>

Creates a webhook

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Endpoint operation

.. raw:: html

   </td>

.. raw:: html

   <td>

/webhooks

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

OAuth scopes

.. raw:: html

   </td>

.. raw:: html

   <td>

webhook_write

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Request object

.. raw:: html

   </td>

.. raw:: html

   <td>

WebhookInfo:

.. raw:: html

   <pre><code class="javascript language-javascript hljs">
   {
      "name": "",
      "scope": "",
      "state": "",
      "webhookSubscriptionEvents": [
         ""
      ],
      "webhookUrlInfo": {
         "url": ""
      },
      "applicationDisplayName": "",
      "applicationName": "",
      "created": "",
      "id": "",
      "lastModified": "",
      "resourceId": "",
      "resourceType": "",
      "status": "",
      "webhookConditionalParams": {
         "webhookAgreementEvents": {
            "includeDetailedInfo": false,
            "includeDocumentsInfo": false,
            "includeParticipantsInfo": false,
            "includeSignedDocuments": false
         },
         "webhookMegaSignEvents": {
            "includeDetailedInfo": false
         },
         "webhookWidgetEvents": {
            "includeDetailedInfo": false,
            "includeDocumentsInfo": false,
            "includeParticipantsInfo": false
         }
      }
   }</code></pre>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Response header

.. raw:: html

   </td>

.. raw:: html

   <td>

Location Header specifying the resource location of the webhook

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Response content type

.. raw:: html

   </td>

.. raw:: html

   <td>

application/json

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Response object

.. raw:: html

   </td>

.. raw:: html

   <td>

WebhookCreationResponse

.. raw:: html

   <pre><code class="javascript language-javascript hljs">{
      "id" : ""
   }</code></pre>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

HTTPS status code

.. raw:: html

   </td>

.. raw:: html

   <td>

201

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Error code

.. raw:: html

   </td>

.. raw:: html

   <td>

Please note that new errors could be returned from APIs or existing error codes can be evolved. Clients are expected to be prepared to do default handling for error scenarios which they do not understand.

.. raw:: html

   <table>

.. raw:: html

   <thead>

.. raw:: html

   <tr>

.. raw:: html

   <th>

HTTPS status code

.. raw:: html

   </th>

.. raw:: html

   <th>

Error code

.. raw:: html

   </th>

.. raw:: html

   <th>

Message

.. raw:: html

   </th>

.. raw:: html

   </tr>

.. raw:: html

   </thead>

.. raw:: html

   <tbody>

.. raw:: html

   <tr>

.. raw:: html

   <td>

400

.. raw:: html

   </td>

.. raw:: html

   <td>

INVALID_ARGUMENTS

.. raw:: html

   </td>

.. raw:: html

   <td>

One or more arguments to the method are invalid.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

400

.. raw:: html

   </td>

.. raw:: html

   <td>

INVALID_WEBHOOK_URL

.. raw:: html

   </td>

.. raw:: html

   <td>

The Webhook URL specified is invalid.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

400

.. raw:: html

   </td>

.. raw:: html

   <td>

INVALID_RESOURCE_ID

.. raw:: html

   </td>

.. raw:: html

   <td>

Resouce Id specified is invalid.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

400

.. raw:: html

   </td>

.. raw:: html

   <td>

INVALID_RESOURCE_TYPE

.. raw:: html

   </td>

.. raw:: html

   <td>

The resource type is invalid.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

400

.. raw:: html

   </td>

.. raw:: html

   <td>

INVALID_WEBHOOK_CONDITIONAL_PARAMS

.. raw:: html

   </td>

.. raw:: html

   <td>

The conditional parameters specified are invalid.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

400

.. raw:: html

   </td>

.. raw:: html

   <td>

MISSING_REQUIRED_PARAM

.. raw:: html

   </td>

.. raw:: html

   <td>

The required parameters are missing.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

400

.. raw:: html

   </td>

.. raw:: html

   <td>

WEBHOOK_LIMIT_EXCEEDED

.. raw:: html

   </td>

.. raw:: html

   <td>

This webhook can’t be created. The events array {events} has reached the maximum number of active webhooks.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

400

.. raw:: html

   </td>

.. raw:: html

   <td>

DUPLICATE_WEBHOOK_CONFIGURATION

.. raw:: html

   </td>

.. raw:: html

   <td>

There is already a webhook registered with same configuration.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

400

.. raw:: html

   </td>

.. raw:: html

   <td>

INVALID_WEBHOOK_STATE

.. raw:: html

   </td>

.. raw:: html

   <td>

The webhook state specified is invalid.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

400

.. raw:: html

   </td>

.. raw:: html

   <td>

INVALID_WEBHOOK_SUBSCRIPTION_EVENTS

.. raw:: html

   </td>

.. raw:: html

   <td>

One or more webhook subscription events specified are invalid.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

403

.. raw:: html

   </td>

.. raw:: html

   <td>

WEBHOOK_CREATION_NOT_ALLOWED

.. raw:: html

   </td>

.. raw:: html

   <td>

Webhook creation is not allowed.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

This API will be used to create a webhook on a particular resouce in Adobe Sign.

-  You need to register the webhook with your application and a user token using this API.
-  Group level webhooks can only be created by a Group admin and Account level webhooks can only be created by an Account admin.
-  The user can customize the events for which the webhook is triggered in this call.

The ``HTTP Location`` header field is returned in the response to provide information about the location of a newly created resource. Multiple webhooks can be created on a single resource. *Also, multiple webhooks can share the same URL.*

GET /webhooks
~~~~~~~~~~~~~

.. raw:: html

   <table>

.. raw:: html

   <thead>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Entity

.. raw:: html

   </th>

.. raw:: html

   <th>

Value

.. raw:: html

   </th>

.. raw:: html

   </tr>

.. raw:: html

   </thead>

.. raw:: html

   <tbody>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Description

.. raw:: html

   </td>

.. raw:: html

   <td>

Get a list of webhooks created by the access token user.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

OAuth scopes

.. raw:: html

   </td>

.. raw:: html

   <td>

webhook_read

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Query parameters

.. raw:: html

   </td>

.. raw:: html

   <td>

.. raw:: html

   <p>

showInactiveWebhooks: boolean: A query parameter to fetch all the inactive webhooks along with the active webhooks.

.. raw:: html

   </p>

::

     <p><code>scope</code>: Scope of the webhook. The possible values are <code>ACCOUNT</code>, <code>GROUP</code>, <code>USER</code>, or <code>RESOURCE</code>.</p>
     <p><code>resourceType</code>: The type of resource on which webhook was created. The possible values are <code>AGREEMENT</code>, <code>WIDGET</code>, and <code>MEGASIGN</code>.</p>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Response content type

.. raw:: html

   </td>

.. raw:: html

   <td>

application/json

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Response object

.. raw:: html

   </td>

.. raw:: html

   <td>

WebhooksInfo

.. raw:: html

   <pre><code class="javascript language-javascript hljs">{
      "userWebhookList": [
         {
            "applicationName": "Application for REST Swagger Documentation",
            "applicationId": "pUQL757H2R2",
            "id": "CBJCHBCAABAAtW5qb_gRDgssqn6tvLvCcav0VqYi0WTR",
            "name": "user level webhook",
            "lastModified": "2018-02-06T22:52:27-08:00",
            "scope": "USER",
            "webhookSubscriptionEvents": [
               "AGREEMENT_RECALLED"
            ],
            "webhookUrlInfo": {
               "url": "https://testUrl"
            },
            "status": "ACTIVE"
         },
         {
            "applicationName": "Application for REST Swagger Documentation",
            "applicationDisplayName ": "REST Swagger",
            "id": "CBJCHBCAABAAtW5qb_gRDgssqn6tvLvCcav0VqYi0WTR",
            "name": "",
            "lastModified": "2018-02-06T22:52:27-08:00",
            "scope": "RESOURCE",
            "resourceType": "AGREEMENT",
            "resourceId": "3dffwifvgvfguierfreokfperfprfppr",
            "webhookSubscriptionEvents": [
               "AGREEMENT_RECALLED"
            ],
            "webhookUrlInfo": {
               "url": "https://testResource"
            },
            "status": "ACTIVE"
         }
      ],
      "page": {
         "nextCursor": " "
      }
   }
           </code></pre>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

HTTPS status code

.. raw:: html

   </td>

.. raw:: html

   <td>

200

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Error code

.. raw:: html

   </td>

.. raw:: html

   <td>

Please note that new errors could be returned from APIs or existing error codes can be evolved. Clients are expected to be prepared to do default handling for error scenarios which they do not understand.

.. raw:: html

   <table>

.. raw:: html

   <thead>

.. raw:: html

   <tr>

.. raw:: html

   <th>

HTTPS status code

.. raw:: html

   </th>

.. raw:: html

   <th>

Error code

.. raw:: html

   </th>

.. raw:: html

   <th>

Message

.. raw:: html

   </th>

.. raw:: html

   </tr>

.. raw:: html

   </thead>

.. raw:: html

   <tbody>

.. raw:: html

   <tr>

.. raw:: html

   <td>

400

.. raw:: html

   </td>

.. raw:: html

   <td>

INVALID_ARGUMENTS

.. raw:: html

   </td>

.. raw:: html

   <td>

One or more arguments to the method are invalid.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

400

.. raw:: html

   </td>

.. raw:: html

   <td>

INVALID_CURSOR

.. raw:: html

   </td>

.. raw:: html

   <td>

The page cursor provided is invalid.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

400

.. raw:: html

   </td>

.. raw:: html

   <td>

INVALID_PAGE_SIZE

.. raw:: html

   </td>

.. raw:: html

   <td>

Page size is either invalid or not within the permissible range.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

GET /webhooks/{webhookId}
~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

   <table>

.. raw:: html

   <thead>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Entity

.. raw:: html

   </th>

.. raw:: html

   <th>

Value

.. raw:: html

   </th>

.. raw:: html

   </tr>

.. raw:: html

   </thead>

.. raw:: html

   <tbody>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Description

.. raw:: html

   </td>

.. raw:: html

   <td>

List details of a webhook.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Endpoint operation

.. raw:: html

   </td>

.. raw:: html

   <td>

/webhhooks/{webhookId}

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

OAuth scopes

.. raw:: html

   </td>

.. raw:: html

   <td>

webhook_read

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Response content type

.. raw:: html

   </td>

.. raw:: html

   <td>

application/json

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Response object

.. raw:: html

   </td>

.. raw:: html

   <td>

WebhookInfo

.. raw:: html

   <pre><code class="javascript language-javascript hljs">{
       "scope": "",
       "webhookSubscriptionEvents": [
           ""
       ],
       "webhookUrlInfo": {
           "url": ""
       },
       "name": "",
       "status": "",
       "applicationDisplayName ": "",
       "applicationName": "",
       "created": "date",
       "id": "",
       "lastModified": "date",
       "resourceId": "",
       "resourceType": "",
       "webhookConditionalParams": {
           "webhookAgreementEvents": {
               "includeDetailedInfo": false,
               "includeDocumentsInfo": false,
               "includeParticipantsInfo": false,
               "includeSignedDocuments": false
           },
           "webhookMegaSignEvents": {
               "includeDetailedInfo": false
           },
           "webhookWidgetEvents": {
               "includeDetailedInfo": false,
               "includeDocumentsInfo": false,
               "includeParticipantsInfo": false
           }
       }
   }</code></pre>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

HTTPS status code

.. raw:: html

   </td>

.. raw:: html

   <td>

200

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Error code

.. raw:: html

   </td>

.. raw:: html

   <td>

Please note that new errors could be returned from APIs or existing error codes can be evolved. Clients are expected to be prepared to do default handling for error scenarios which they do not understand.

.. raw:: html

   <table>

.. raw:: html

   <thead>

.. raw:: html

   <tr>

.. raw:: html

   <th>

HTTPS status code

.. raw:: html

   </th>

.. raw:: html

   <th>

Error code

.. raw:: html

   </th>

.. raw:: html

   <th>

Message

.. raw:: html

   </th>

.. raw:: html

   </tr>

.. raw:: html

   </thead>

.. raw:: html

   <tbody>

.. raw:: html

   <tr>

.. raw:: html

   <td>

304

.. raw:: html

   </td>

.. raw:: html

   <td>

RESOURCE_NOT_MODIFIED

.. raw:: html

   </td>

.. raw:: html

   <td>

The resource is not modified.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

404

.. raw:: html

   </td>

.. raw:: html

   <td>

INVALID_WEBHOOK_ID

.. raw:: html

   </td>

.. raw:: html

   <td>

The webhookId specified is invalid.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

PUT /webhooks/{webhookId}
~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

   <table>

.. raw:: html

   <thead>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Entity

.. raw:: html

   </th>

.. raw:: html

   <th>

Value

.. raw:: html

   </th>

.. raw:: html

   </tr>

.. raw:: html

   </thead>

.. raw:: html

   <tbody>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Description

.. raw:: html

   </td>

.. raw:: html

   <td>

This endpoint is used to update the webhook resource.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Endpoint operation

.. raw:: html

   </td>

.. raw:: html

   <td>

/webhooks/{webhookId}

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

OAuth scopes

.. raw:: html

   </td>

.. raw:: html

   <td>

webhook_write

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Request header

.. raw:: html

   </td>

.. raw:: html

   <td>

Standard header. Additionally, If-Match headers, which will be processed as per the Concurrency section of the DC API Guidelines

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Request body

.. raw:: html

   </td>

.. raw:: html

   <td>

WebhookInfo

.. raw:: html

   <pre><code class="javascript language-javascript hljs">{
      "name": "",
      "scope": "",
      "state": "",
      "webhookSubscriptionEvents": [
         ""
      ],
      "webhookUrlInfo": {
         "url": ""
      },
      "applicationDisplayName": "",
      "applicationName": "",
      "created": "",
      "id": "",
      "lastModified": "",
      "resourceId": "",
      "resourceType": "",
      "status": "",
      "webhookConditionalParams": {
         "webhookAgreementEvents": {
            "includeDetailedInfo": false,
            "includeDocumentsInfo": false,
            "includeParticipantsInfo": false,
            "includeSignedDocuments": false
         },
         "webhookMegaSignEvents": {
            "includeDetailedInfo": false
         },
         "webhookWidgetEvents": {
            "includeDetailedInfo": false,
            "includeDocumentsInfo": false,
            "includeParticipantsInfo": false
         }
      }
   }</code></pre>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Response content type

.. raw:: html

   </td>

.. raw:: html

   <td>

application/json

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Response object

.. raw:: html

   </td>

.. raw:: html

   <td>

Empty response

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

HTTPS status code

.. raw:: html

   </td>

.. raw:: html

   <td>

204

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Error code

.. raw:: html

   </td>

.. raw:: html

   <td>

Please note that new errors could be returned from APIs or existing error codes can be evolved. Clients are expected to be prepared to do default handling for error scenarios which they do not understand.

.. raw:: html

   </p>

::

       <table>
         <thead>
           <tr>
             <th>HTTPS status code </th>
             <th>Error code</th>
             <th>Message</th>
           </tr>
         </thead>
         <tbody>
           <tr>
             <td>400</td>
             <td><code>MISSING_REQUIRED_PARAM</code></td>
             <td>Required parameters are missing.</td>
           </tr>
           <tr>
             <td>400</td>
             <td><code>DUPLICATE_WEBHOOK_CONFIGURATION</code></td>
             <td>There is already a webhook registered with same configuration.</td>
           </tr>
           <tr>
             <td>400</td>
             <td><code>INVALID_JSON</code></td>
             <td>An invalid JSON was specified.</td>
           </tr>
           <tr>
             <td>400</td>
             <td><code>INVALID_WEBHOOK_CONDITIONAL_PARAMS</code></td>
             <td>The webhook conditional parameters specified are invalid.</td>
           </tr>
           <tr>
             <td>400</td>
             <td><code>INVALID_WEBHOOK_SUBSCRIPTION_EVENTS</code></td>
             <td>One or more webhook subscription events specified are invalid.</td>
           </tr>
           <tr>
             <td>400</td>
             <td><code>MISSING_IF_MATCH_HEADER</code></td>
             <td>The If-Match header missing.</td>
           </tr>
           <tr>
             <td>400</td>
             <td><code>UPDATE_NOT_ALLOWED</code></td>
             <td>The webhook you are trying to update cannot be modified.</td>
           </tr>
           <tr>
             <td>400</td>
             <td><code>WEBHOOK_LIMIT_EXCEEDED</code></td>
             <td>This webhook can&rsquo;t be activated. The resource has reached the maximum number of active webhooks.</td>
           </tr>
           <tr>
             <td>404</td>
             <td><code>INVALID_WEBHOOK_ID</code></td>
             <td>The <code>webhookId</code> is invalid.</td>
           </tr>
           <tr>
             <td>412</td>
             <td><code>RESOURCE_MODIFIED</code></td>
             <td>The resource is already modified with a newer version.</td>
           </tr>
         </tbody>
       </table></td>
   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

Only events and conditional parameters can be modified. The webhook URL can’t be modified once the webhook is created. The modification can also be done in the INACTIVE state.

PUT /webhooks/{webhookId}/state
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

   <table>

.. raw:: html

   <thead>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Entity

.. raw:: html

   </th>

.. raw:: html

   <th>

Value

.. raw:: html

   </th>

.. raw:: html

   </tr>

.. raw:: html

   </thead>

.. raw:: html

   <tbody>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Description

.. raw:: html

   </td>

.. raw:: html

   <td>

This endpoint will update the state of a webhook identified by webhookId in the path.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Endpoint operation

.. raw:: html

   </td>

.. raw:: html

   <td>

/webhooks/{webhookId}/state

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

OAuth scopes

.. raw:: html

   </td>

.. raw:: html

   <td>

webhook_write

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Request header

.. raw:: html

   </td>

.. raw:: html

   <td>

Standard header. Additionally, If-Match headers, which will be processed as per the Concurrency section of the DC API Guidelines.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Request body

.. raw:: html

   </td>

.. raw:: html

   <td>

WebhookInfo

.. raw:: html

   <pre><code class="javascript language-javascript hljs">{
      "state": ""
   }</code></pre>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Response content type

.. raw:: html

   </td>

.. raw:: html

   <td>

application/json

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Response object

.. raw:: html

   </td>

.. raw:: html

   <td>

Empty response

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

HTTPS status code

.. raw:: html

   </td>

.. raw:: html

   <td>

204

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Error code

.. raw:: html

   </td>

.. raw:: html

   <td>

Please note that new errors could be returned from APIs or existing error codes can be evolved. Clients are expected to be prepared to do default handling for error scenarios which they do not understand.

.. raw:: html

   </p>

::

       <table>
           <thead>
               <tr>
                   <th>HTTPS status code</th>
                   <th>Error code</th>
                   <th>Message</th>
               </tr>
           </thead>
         <tbody>
           <tr>
             <td>400</td>
             <td><code>MISSING_REQUIRED_PARAM</code></td>
             <td>Required parameters are missing. </td>
           </tr>
           <tr>
             <td>400</td>
             <td><code>DUPLICATE_WEBHOOK_CONFIGURATION</code></td>
             <td>There is already a webhook registered with same configuration.</td>
           </tr>
           <tr>
             <td>400</td>
             <td><code>INVALID_JSON</code></td>
             <td>An invalid JSON was specified.</td>
           </tr>
           <tr>
             <td>400</td>
             <td><code>MISSING_IF_MATCH_HEADER</code></td>
             <td>The If-Match header is missing.</td>
           </tr>
           <tr>
             <td>400</td>
             <td><code>UPDATE_NOT_ALLOWED</code></td>
             <td>The webhook you are trying to update cannot be modified.</td>
           </tr>
           <tr>
             <td>400</td>
             <td><code>WEBHOOK_LIMIT_EXCEEDED</code></td>
             <td>This webhook can&rsquo;t be activated. The resource has reached the maximum number of active webhooks.</td>
           </tr>
           <tr>
             <td>404</td>
             <td><code>INVALID_WEBHOOK_ID</code></td>
             <td>The <code>webhookId</code> is invalid.</td>
           </tr>
           <tr>
             <td>412</td>
             <td><code>RESOURCE_MODIFIED</code></td>
             <td>The resource is already modified with a newer version.</td>
           </tr>
         </tbody>
       </table></td>
   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

DELETE /webhooks/{webhookId}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. raw:: html

   <table>

.. raw:: html

   <thead>

.. raw:: html

   <tr>

.. raw:: html

   <th>

Entity

.. raw:: html

   </th>

.. raw:: html

   <th>

Value

.. raw:: html

   </th>

.. raw:: html

   </tr>

.. raw:: html

   </thead>

.. raw:: html

   <tbody>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Description

.. raw:: html

   </td>

.. raw:: html

   <td>

This endpoint is used to delete the webhook resource. This is the terminal state of the webhook and the action is irreversible.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Endpoint operation

.. raw:: html

   </td>

.. raw:: html

   <td>

/webhooks/{webhookId}

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

OAuth scopes

.. raw:: html

   </td>

.. raw:: html

   <td>

webhook_delete

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Request header

.. raw:: html

   </td>

.. raw:: html

   <td>

Standard header

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

HTTPS status code

.. raw:: html

   </td>

.. raw:: html

   <td>

204

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

Error code

.. raw:: html

   </td>

.. raw:: html

   <td>

Please note that new errors could be returned from APIs or existing error codes can be evolved. Clients are expected to be prepared to do default handling for error scenarios which they do not understand.

.. raw:: html

   <table>

.. raw:: html

   <thead>

.. raw:: html

   <tr>

.. raw:: html

   <th>

HTTPS status code

.. raw:: html

   </th>

.. raw:: html

   <th>

Error code

.. raw:: html

   </th>

.. raw:: html

   <th>

Message

.. raw:: html

   </th>

.. raw:: html

   </tr>

.. raw:: html

   </thead>

.. raw:: html

   <tbody>

.. raw:: html

   <tr>

.. raw:: html

   <td>

403

.. raw:: html

   </td>

.. raw:: html

   <td>

FORBIDDEN

.. raw:: html

   </td>

.. raw:: html

   <td>

Delete is not allowed.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   <tr>

.. raw:: html

   <td>

404

.. raw:: html

   </td>

.. raw:: html

   <td>

INVALID_WEBHOOK_ID

.. raw:: html

   </td>

.. raw:: html

   <td>

The webhookId is invalid.

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

.. raw:: html

   </td>

.. raw:: html

   </tr>

.. raw:: html

   </tbody>

.. raw:: html

   </table>

Standard error codes in every API request
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Any API request may return any of these standard error codes:

+-----------------------+--------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| **HTTPS status code** | **Error code**                       | **Message**                                                                                                                                                      |
+=======================+======================================+==================================================================================================================================================================+
| 400                   | ``BAD_REQUEST``                      | The request provided is invalid.                                                                                                                                 |
+-----------------------+--------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 400                   | ``INVALID_JSON``                     | An invalid JSON was specified.                                                                                                                                   |
+-----------------------+--------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 400                   | ``INVALID_ON_BEHALF_OF_USER_HEADER`` | The value provided in the ``x-on-behalf-of-user`` header is in invalid format.                                                                                   |
+-----------------------+--------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 400                   | ``INVALID_X_API_USER_HEADER``        | The value provided in ``x-api-user`` header is in invalid format.                                                                                                |
+-----------------------+--------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 400                   | ``MISC_ERROR``                       | Some miscellaneous error has occurred.                                                                                                                           |
+-----------------------+--------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 401                   | ``UNAUTHORIZED``                     | You cannot work on behalf of this user.                                                                                                                          |
+-----------------------+--------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 401                   | ``UNVERIFIED_USER``                  | The user has registered but has not verified their email address. The user must use the Adobe Sign web site to complete verification.                            |
+-----------------------+--------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 401                   | ``NO_AUTHORIZATION_HEADER``          | The authorization header was not provided.                                                                                                                       |
+-----------------------+--------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 401                   | ``INVALID_ACCESS_TOKEN``             | The access token provided is invalid or has expired.                                                                                                             |
+-----------------------+--------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 401                   | ``INVALID_USER``                     | An invalid user ID or email was provided in the ``x-user`` header.                                                                                               |
+-----------------------+--------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 401                   | ``INVALID_ON_BEHALF_OF_USER``        | An invalid user ID or email was provided in the ``x-on-behalf-of-user`` header.                                                                                  |
+-----------------------+--------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 403                   | ``API_TERMS_NOT_ACCEPTED``           | Your account is locked because an administrator has not agreed to Adobe Sign’s Terms of Use. Please contact your account administrator to activate your account. |
+-----------------------+--------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 404                   | ``PERMISSION_DENIED``                | The API caller does not have the permission to execute this operation.                                                                                           |
+-----------------------+--------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| 500                   | ``MISC_SERVER_ERROR``                | Some miscellaneous server error has occurred.                                                                                                                    |
+-----------------------+--------------------------------------+------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Standard headers in every API request
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Every API request will have the following standard headers. If Any API in the list above does not have one or more of the following headers, the API will explicitly document this fact.

+-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| **Header Name**                   | **Description**                                                                                                                                                                                        |
+===================================+========================================================================================================================================================================================================+
| ``AUTHORIZATION``                 | An access token with the correct scopes.                                                                                                                                                               |
+-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| ``x-api-user``                    | The userId or email of the API caller using the account or group token in the format ``userid:{userId}`` **OR** ``email:{email}.`` If it is not specified, then the caller is inferred from the token. |
+-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| ``x-on-behalf-of-user``           | Account sharing: The user on whose behalf the API caller is working.                                                                                                                                   |
+-----------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
