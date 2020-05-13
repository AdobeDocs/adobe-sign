# Migrating From SOAP

If you are using the legacy Adobe Sign SOAP APIs, we highly recommend migrating your apps to consume the v6 REST APIs. 
The list below shows the SOAP endpoints with their REST equivalents. Both endpoints link directly to the full method descripotion.

## General-purpose Methods

| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `getBaseUris` | /baseUris, GET  |

**Note:** Base URIs: API calls starting v5 of REST API must be made on a specific base URL obtained either from the api\_access\_point returned from the OAuth workflow or by making a call to the `GET /baseUris` endpoint. 

## Document Methods

| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `sendDocument` | /agreements, POST | 


SenderInfo is represented through `x-api-user`. Files are specified through /transientDocuments. 
&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `sendDocumentInteractive` | /agreements/{agrId}/views, POST | 

From v6 onwards, the interactive views can be specified and obtained from the `POST /agreements/{agrId}/views` endpoint for the interactive behavior. 
&nbsp;  
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
`sendDocumentMegaSign` | /megaSigns, POST | 

MegaSign allows sending the same agreement to multiple recipients and creating a separate instance of agreement for each recipient. 
&nbsp;  
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `createLibraryDocument` | /libraryDocuments, POST |
&nbsp;  
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `createLibraryDocumentInteractive` | /libraryDocuments/{libraryDocumentId}, POST | 

From v6 onwards, the interactive views can be specified and obtained from the `POST /agreements/{agrId}/views` endpoint for the interactive behavior. 
&nbsp;  
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `sendReminder` | agreements/{agrId}/reminders, POST |   
&nbsp;  
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `removeDocument` | /agreements/{agrId}/documents, DELETE | 

To delete the documents of agreements, use the `DELETE /agreements/{agrId}/documents` endpoint; and to remove it from Manage Page(GET /agreements), use `PUT /agreements/{agrId}/visibility` 
&nbsp;  
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `cancelDocument` | /agreements/{agrId}/state, PUT | 

Cancel: Called by sender. 
&nbsp;  
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `rejectDocument` | /agreements/{agrId}/members/participantSets/{psId}/participants/{pId}/reject, PUT | 

Reject: Called by current signer. 
&nbsp;  
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `replaceSigner` | /agreements/{agreementId}/members/participantSets/{participantSetId}, PUT | 

Replace: Called by sender. Both the original signer and new one can sign.
&nbsp;  
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `delegateSigning` | /agreements/{agrId}/participantSets/{psId}/ participants/{pId}/delegatedParticipantSet, POST | 

Delegate: Called by signer. Both the delegator and delegatee can sign. 



## Status Methods

| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `getDocumentInfo` | /agreements/{agrId}, GET | 

In SOAP API, `getDocumentInfo`, `getDocuments`, `getAuditTrail` etc. work on `documentKeys`, which can be an ID for an agreement, widget, or library document. The REST API demarcates these as separate resources (cleaner design and strongly typed) and hence, based on the kind of resource you are working on, there is a corresponding /libraryDocuments, /widgets to these. Example: `/widgets/{widgetId}, GET` will getDocumentInfo for `widgetId`, and similarly for documents, audit trail, etc. 
&nbsp;  
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `getDocumentInfosByExternalId` | /agreements, GET query = externalId | 

`externalId` can be used to map your internal IDs to eSign IDs. 
&nbsp;  
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `getDocuments` | /agreements/{agrId}/documents, GET | 

REST returns a list of document IDs that can be provided to the following endpoint to get a document stream. 
&nbsp;  
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `getDocumentUrls` | /agreements/{agrId}/combinedDocument/url, GET | 

Retrieve the URL of the combined document. 

&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `getDocumentUrls` | /agreements/{agrId}/documents/{docId}/url, GET | 

Retrieve the URL of an individual document. 

&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `getDocumentImageUrls` | /agreements/{agrId}/documents/imageUrls, GET | 

Retrieve the image URLs of all the visible pages of an agreement. 

&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `getDocumentImageUrls` | /agreements/{agrId}/documents/{docId}/imageUrls, GET | 

Retrieve image URLs of all the visible pages of an agreement&rsquo;s document. 

&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `getSupportingDocuments` | /agreements/{agrId}/documents, GET | 

Can also specify the content format. 

&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `getFormData` | /agreements/{agrId}/formData, GET | 

Returns a CSV file stream. 

&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `getAuditTrail` | /agreements/{agrId}/auditTrail, GET |   

&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `getSigningUrl` | /agreements/{agrId}/signingUrls, GET |   

&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `getEmbeddedView` | /agreements/{agrId}/views, POST | 

Use the name = DOCUMENT to get the embedded view of an agreement. 

&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `getMyDocuments` | /agreements, GET |   

&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `getUserDocuments` | /agreements, GET | 

Use `x-api-user` for specifying the user whose agreements are to be retrieved. 

&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `getMyLibraryDocuments` | /libraryDocuments, GET |   

&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `getLibraryDocumentsForUser` | /libraryDocuments, GET | 

Use `x-api-user` for specifying the user whose library documents are to be retrieved. 

&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `getMyWidgets` | /widgets, GET |   

&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `getWidgetsForUser` | /widgets, GET | 

Use `x-api-user` for specifying the user whose widgets are to be retrieved. 

&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `getMegaSignDocument` | /megaSigns/{megaSignId}/agreements, GET | 

Get all child agreement IDs of the parent MegaSign. 

&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `getUsersInAccount` | /users, GET |   

&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `getGroupsInAccount` | /groups, GET |   

&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `getUsersInGroups` | /groups/{groupId}/users, GET |   

&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `moveUsersToGroup` | /users/{userId}/groups, PUT | 

Specify the new `groupId` in the request. 

&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `getUserInfo` | /users/{userId}, GET |   

&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `createEmbeddedWidget` | /widgets, POST |   

&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `createUrlWidget` | /widgets, POST |   

&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `disableWidget` | /widgets/{widgetId}/state, PUT | 

Use status value as `INACTIVE`. 

&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| `enableWidget` | /widgets/{widgetId}/state, PUT | 

Use status value as `ACTIVE`. 
