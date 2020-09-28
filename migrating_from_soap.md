# Migrating From SOAP

If you are using the legacy Adobe Sign SOAP APIs, we highly recommend migrating your apps to consume the v6 REST APIs. 
The list below shows the SOAP endpoints with their REST equivalents. Both endpoints link directly to the full method description.
* [General-purpose Methods](#general-purpose-methods)
* [Document Methods](#document-methods)
* [Status Methods](#status-methods)
* [User Methods](#user-methods)
* [Web Form Methods](#web-form-methods)
* [Test Methods](#test-methods)
* [Deprecated Methods](#deprecated-methods-from-legacy-soap-versions)

&nbsp;
## General-purpose Methods:
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getBaseUris**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#getBaseUris) | [/baseUris, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/baseUris/getBaseUris)  |

**Note:** Base URIs: API calls starting v5 of REST API must be made on a specific base URL obtained either from the api\_access\_point returned from the OAuth workflow or by making a call to the `GET /baseUris` endpoint. 

&nbsp;  
&nbsp; 
## Document Methods:
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**sendDocument**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#sendDocument) | [/agreements, POST](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/createAgreement) | 


SenderInfo is represented through `x-api-user`. Files are specified through /transientDocuments. 
&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**sendDocumentInteractive**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#sendDocumentInteractive) | [/agreements/{agrId}/views, POST](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/createAgreementView) | 

From v6 onwards, the interactive views can be specified and obtained from the `POST /agreements/{agrId}/views` endpoint for the interactive behavior. 
&nbsp;  
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
[**sendDocumentMegaSign**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#sendDocumentMegaSign) | [/megaSigns, POST](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/megaSigns/createMegaSign) | 

MegaSign allows sending the same agreement to multiple recipients and creating a separate instance of agreement for each recipient. 
&nbsp;  
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**createLibraryDocument**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#createLibraryDocument) | [/libraryDocuments, POST](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/libraryDocuments/createLibraryDocument) |
    
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**createLibraryDocumentInteractive**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#createLibraryDocumentInteractive) |  [/libraryDocuments/{libraryDocumentId}, POST](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/libraryDocuments/createLibraryDocumentView) | 

From v6 onwards, the interactive views can be specified and obtained from the `POST /agreements/{agrId}/views` endpoint for the interactive behavior. 
&nbsp;  
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**sendReminder**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#sendReminder) | [/agreements/{agrId}/reminders, POST](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/createReminderOnParticipant) |   

&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**removeDocument**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#removeDocument) | [/agreements/{agrId}/documents, DELETE](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/deleteDocuments) | 

To delete the documents of agreements, use the `DELETE /agreements/{agrId}/documents` endpoint; and to remove it from Manage Page(GET /agreements), use `PUT /agreements/{agrId}/visibility` 
&nbsp;  
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**cancelDocument**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#cancelDocument) | [/agreements/{agrId}/state, PUT](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/updateAgreementState) | 

Cancel: Called by sender. 
&nbsp;  
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**rejectDocument**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#rejectDocument) | [/agreements/{agrId}/members/participantSets/{psId}/participants/{pId}/reject, PUT](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/rejectAgreementForParticipation) | 

Reject: Called by current signer. 
&nbsp;  
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**replaceSigner**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#replaceSigner) | [/agreements/{agreementId}/members/participantSets/{participantSetId}, PUT](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/updateParticipantSet) | 

Replace: Called by sender. Both the original signer and new one can sign.
&nbsp;  
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**delegateSigning**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#delegateSigning) | [/agreements/{agrId}/members/participantSets/{psId}/ participants/{pId}/delegatedParticipantSet, POST](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/createDelegatedParticipantSets) | 

Delegate: Called by signer. Both the delegator and delegatee can sign. 
&nbsp;  
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
|  [**notifyDocumentVaulted**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#notifyDocumentVaulted) |  Expected in the June 2020 release  |


&nbsp;  
&nbsp; 
## Status Methods:
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getDocumentInfo**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#getDocumentInfo) | [/agreements/{agrId}, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/getAgreementInfo) | 

In SOAP API, `getDocumentInfo`, `getDocuments`, `getAuditTrail` etc. work on `documentKeys`, which can be an ID for an agreement, widget, or library document. The REST API demarcates these as separate resources (cleaner design and strongly typed) and hence, based on the kind of resource you are working on, there is a corresponding /libraryDocuments, /widgets to these. Example: `/widgets/{widgetId}, GET` will getDocumentInfo for `widgetId`, and similarly for documents, audit trail, etc. 
&nbsp;  
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getDocumentInfosByExternalId**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#getDocumentInfosByExternalId) | [/agreements, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/getAgreements) query = externalId | 

`externalId` can be used to map your internal IDs to Adobe Sign IDs. 
&nbsp;  
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getDocuments**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#getDocuments) | [/agreements/{agrId}/documents, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/getAllDocuments) | 

REST returns a list of document IDs that can be provided to the following endpoint to get a document stream. 
&nbsp;  
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getDocumentUrls**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#getDocumentUrls) | [/agreements/{agrId}/combinedDocument/url, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/getCombinedDocumentUrl) | 

Retrieve the URL of the **combined document**. 
&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getDocumentUrls**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#getDocumentUrls) | [/agreements/{agrId}/documents/{docId}/url, GET](https://secure.na1.adobesign.com/public/docs/restapi/v5#!/agreements/getDocumentUrl) | 

Retrieve the URL of an **individual document**. 
&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getDocumentImageUrls**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#getDocumentImageUrls) | [/agreements/{agrId}/documents/imageUrls, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/getAllDocumentsImageUrls) | 

Retrieve the image URLs of **all visible pages** of an agreement. 
&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getDocumentImageUrls**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#getDocumentImageUrls)  | [/agreements/{agrId}/documents/{docId}/imageUrls, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/getDocumentImageUrls) | 

Retrieve image URLs of a specified documentID. 
&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getSupportingDocuments**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#getSupportingDocuments) | [/agreements/{agrId}/documents, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/getAllDocuments) | 

Can also specify the content format. 
&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getFormData**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#getFormData) | [/agreements/{agrId}/formData, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/getFormData) | 

Returns a CSV file stream. 
&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getAuditTrail**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#getAuditTrail) | [/agreements/{agrId}/auditTrail, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/getAuditTrail) |   
    
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getSigningUrl**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#getSigningUrl) | [/agreements/{agrId}/signingUrls, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/getSigningUrl) |   





&nbsp;  
&nbsp; 
## User Methods:
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**createUser**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService19#createUser) | **v5 REST Only** [/users, POST](https://secure.na1.adobesign.com/public/docs/restapi/v5#!/users/createUser) |   
 
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**verifyUser**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#verifyUser) | [/users/{userId}, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/users/getUserDetail)| 

The REST equivalent can be used to see if the user exists, but does not support password verification.

&nbsp;
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**searchUserDocuments**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#searchUserDocuments) | TBD | 

&nbsp;
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getDocumentEventsForUser**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#getDocumentEventsForUser) | [/agreement/{agrId}/events, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/getEvents) | 

&nbsp;
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getEmbeddedView**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#getEmbeddedView) | [/agreements/{agrId}/views, POST](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/createAgreementView) | 

Use the name = DOCUMENT to get the embedded view of an agreement. 

&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getUserDocuments**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#getUserDocuments) | [/agreements, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/getAgreements) | 

&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getMyDocuments**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#getMyDocuments) | [/agreements, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/getAgreements) |   

Use `x-api-user` for specifying the user whose agreements are to be retrieved. 

&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getLibraryDocumentsForUser**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#getLibraryDocumentsForUser) | [/libraryDocuments, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/libraryDocuments/getLibraryDocuments) | 
 
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getMyLibraryDocuments**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#getMyLibraryDocuments) | [/libraryDocuments, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/libraryDocuments/getLibraryDocuments) |   

Use `x-api-user` for specifying the user whose library documents are to be retrieved. 

&nbsp; 
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getWidgetsForUser**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#getWidgetsForUser) | [/widgets, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/widgets/getWidgets) | 

 
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getMyWidgets**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#getMyWidgets) | [/widgets, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/widgets/getWidgets) |   

Use `x-api-user` for specifying the user whose widgets are to be retrieved. 
&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getMegaSignDocument**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#getMegaSignDocument) | [/megaSigns/{megaSignId}/agreements, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/megaSigns/getMegaSignChildAgreements) | 

Get all child agreement IDs of the parent MegaSign. 
&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getUsersInAccount**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#getUsersInAccount) | [/users, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/users/getUsers) |   
 
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**createGroup**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#createGroup) | **v5 REST Only** [/groups, POST](https://secure.na1.adobesign.com/public/docs/restapi/v5#!/groups/createGroup) |   
 
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**deleteGroup**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#deleteGroup) | **v5 REST Only** [/groups/groupId, DELETE](https://secure.na1.adobesign.com/public/docs/restapi/v5#!/groups/deleteGroup) |   
 
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**renameGroup**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#renameGroup) | **v5 REST Only** [/groups/{groupId}, PUT](https://secure.na1.adobesign.com/public/docs/restapi/v5#!/groups/modifyGroup) |   
 
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getGroupsInAccount**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#getGroupsInAccount) | [/groups, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/groups/getGroups) |   
 
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getUsersInGroups**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#getUsersInGroup) | [/groups/{groupId}/users, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/groups/getUsersInGroup) |   

&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**moveUsersToGroup**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#moveUsersToGroup) | [/users/{userId}/groups, PUT](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/users/updateGroupsOfUser) | 

Specify the new `groupId` in the request. 
&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getUserInfo**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#getUserInfo) | [/users/{userId}, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/users/getUserDetail) |   

&nbsp; 
&nbsp; 
## Web Form Methods:  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**createEmbeddedWidget**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#createEmbeddedWidget) | [/widgets, POST](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/widgets/createWidget) |

&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**createPersonalEmbeddedWidget**]( https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#createPersonalEmbeddedWidget) | [/widgets/{widgetId/views, POST](https://secure.na1.echosign.com/public/docs/restapi/v6#!/widgets/getWidgetView) |   
 
&nbsp; 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**personalizeEmbeddedWidget**]( https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#personalizeEmbeddedWidget) | [/widgets, POST](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/widgets/createWidget)  |  
 
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**createUrlWidget**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#createUrlWidget) | [/widgets, POST](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/widgets/createWidget) |   
 
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**createPersonalUrlWidget**]( https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#createPersonalUrlWidget) |  [/widgets/{widgetId/views, POST](https://secure.na1.echosign.com/public/docs/restapi/v6#!/widgets/getWidgetView) | 
 
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**personalizeUrlWidget**]( https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#personalizeUrlWidget) | [/widgets, POST](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/widgets/createWidget)  |   
 
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**disableWidget**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#disableWidget) | [/widgets/{widgetId}/state, PUT](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/widgets/updateWidgetState) | 

Use status value as `INACTIVE`. 
&nbsp;  
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**enableWidget**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#enableWidget) | [/widgets/{widgetId}/state, PUT](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/widgets/updateWidgetState) | 

Use status value as `ACTIVE`. 

&nbsp;  
&nbsp; 

| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**personalizeEmbeddedWidget**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService19#personalizeEmbeddedWidget) | [/widgets, POST](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/widgets/createWidget)
 
&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**personalizeUrlWidget**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService19#personalizeUrlWidget) | [/widgets, POST](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/widgets/createWidget)|
 
&nbsp;  
&nbsp;
## Test Methods: 
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**testPing**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#testPing)   |  [/baseURIs, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/baseUris/getBaseUris)   |

&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**testEchoFile**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService22#testEchoFile)    |  TBD   |

&nbsp;  
&nbsp; 
## Deprecated Methods from legacy SOAP versions:
### Access Methods:
* issueAccessToken - [OAuth has replaced access tokens](https://www.adobe.io/apis/documentcloud/sign/docs.html#!adobedocs/adobe-sign/master/gstarted/configure_oauth.md).

&nbsp; 
### Document Methods:
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**initiateInteractiveSendDocument**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService13#initiateInteractiveSendDocument) | [/agreements/{agrId}/views, POST](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/createAgreementView) |

&nbsp; 
### Status Methods:
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getDocumentUrlByVersion**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService13#getDocumentUrlByVersion)    |  [/agreement/{agreementID}/combinedDocument/url, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/getCombinedDocumentUrl) |

&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getDocumentByVersion**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService13#getDocumentByVersion)    |  [/agreements/{agreementId}/combinedDocument, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/getCombinedDocument)  | 

&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getImagesByVersion**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService13#getImagesByVersion) | [/agreements/{agrId}/documents/imageUrls, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/getAllDocumentsImageUrls) |

&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getLatestDocument**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService13#getLatestDocument) | [/agreements/{agrId}/documents, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/getAllDocuments) |
 
&nbsp;
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getLatestDocumentUrl**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService13#getLatestDocumentUrl) | [/agreements/{agrId}/documents/{docId}/url, GET]()<br/>[/agreements/{agrId}/combinedDocument/url, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/getCombinedDocumentUrl) |

&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getLatestImages**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService13#getLatestImages) | [/agreements/{agrId}/documents/imageUrls, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/getAllDocumentsImageUrls)<br/>[/agreements/{agrId}/documents/{docId}/imageUrls, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/getDocumentImageUrls) |
 
&nbsp;  
### User Methods:
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**getDocumentsForUser**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService13#getDocumentsForUser) | [/agreements, GET](https://secure.na1.adobesign.com/public/docs/restapi/v6#!/agreements/getAgreements) |

&nbsp;  
| **SOAP Endpoint** | **REST Endpoint**  |
| :---    |  :----   |
| [**createAccount**](https://secure.na1.adobesign.com/public/docs/EchoSignDocumentService19#createAccount) | None |
