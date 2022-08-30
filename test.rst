Migrating From SOAP
===================

Remove me. 

If you are using the legacy Adobe Sign SOAP APIs, we highly recommend migrating your apps to consume the v6 REST APIs. The list below shows the SOAP endpoints with their REST equivalents. Both endpoints link directly to the full method description. \* `General-purpose Methods <#general-purpose-methods>`__ \* `Document Methods <#document-methods>`__ \* `Status Methods <#status-methods>`__ \* `User Methods <#user-methods>`__ \* `Web Form Methods <#web-form-methods>`__ \* `Test Methods <#test-methods>`__ \* `Deprecated Methods <#deprecated-methods-from-legacy-soap-versions>`__

  ## General-purpose Methods: \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getBaseUris <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#getBaseUris>`__ \| `/baseUris, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/baseUris/getBaseUris>`__ \|

**Note:** Base URIs: API calls starting v5 of REST API must be made on a specific base URL obtained either from the api_access_point returned from the OAuth workflow or by making a call to the ``GET /baseUris`` endpoint.

|  
|   ## Document Methods: \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `sendDocument <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#sendDocument>`__ \| `/agreements, POST <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/createAgreement>`__ \|

| SenderInfo is represented through ``x-api-user``. Files are specified through /transientDocuments.  
|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `sendDocumentInteractive <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#sendDocumentInteractive>`__ \| `/agreements/{agrId}/views, POST <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/createAgreementView>`__ \|

| From v6 onwards, the interactive views can be specified and obtained from the ``POST /agreements/{agrId}/views`` endpoint for the interactive behavior.  
|   \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| `sendDocumentMegaSign <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#sendDocumentMegaSign>`__ \| `/megaSigns, POST <https://secure.na1.echosign.com/public/docs/restapi/v6#!/megaSigns/createMegaSign>`__ \|

| MegaSign allows sending the same agreement to multiple recipients and creating a separate instance of agreement for each recipient.  
|   \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `createLibraryDocument <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#createLibraryDocument>`__ \| `/libraryDocuments, POST <https://secure.na1.echosign.com/public/docs/restapi/v6#!/libraryDocuments/createLibraryDocument>`__ \|

  \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `createLibraryDocumentInteractive <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#createLibraryDocumentInteractive>`__ \| `/libraryDocuments/{libraryDocumentId}, POST <https://secure.na1.echosign.com/public/docs/restapi/v6#!/libraryDocuments/createLibraryDocumentView>`__ \|

| From v6 onwards, the interactive views can be specified and obtained from the ``POST /agreements/{agrId}/views`` endpoint for the interactive behavior.  
|   \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `sendReminder <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#sendReminder>`__ \| `/agreements/{agrId}/reminders, POST <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/createReminderOnParticipant>`__ \|

  \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `removeDocument <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#removeDocument>`__ \| `/agreements/{agrId}/documents, DELETE <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/deleteDocuments>`__ \|

| To delete the documents of agreements, use the ``DELETE /agreements/{agrId}/documents`` endpoint; and to remove it from Manage Page(GET /agreements), use ``PUT /agreements/{agrId}/visibility``  
|   \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `cancelDocument <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#cancelDocument>`__ \| `/agreements/{agrId}/state, PUT <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/updateAgreementState>`__ \|

| Cancel: Called by sender.  
|   \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `rejectDocument <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#rejectDocument>`__ \| `/agreements/{agrId}/members/participantSets/{psId}/participants/{pId}/reject, PUT <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/rejectAgreementForParticipation>`__ \|

| Reject: Called by current signer.  
|   \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `replaceSigner <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#replaceSigner>`__ \| `/agreements/{agreementId}/members/participantSets/{participantSetId}, PUT <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/updateParticipantSet>`__ \|

| Replace: Called by sender. Both the original signer and new one can sign.  
|   \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `delegateSigning <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#delegateSigning>`__ \| `/agreements/{agrId}/members/participantSets/{psId}/ participants/{pId}/delegatedParticipantSet, POST <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/createDelegatedParticipantSets>`__ \|

| Delegate: Called by signer. Both the delegator and delegatee can sign.  
|   \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `notifyDocumentVaulted <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#notifyDocumentVaulted>`__ \| Expected in the June 2020 release \|

|  
|   ## Status Methods: \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getDocumentInfo <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#getDocumentInfo>`__ \| `/agreements/{agrId}, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/getAgreementInfo>`__ \|

| In SOAP API, ``getDocumentInfo``, ``getDocuments``, ``getAuditTrail`` etc. work on ``documentKeys``, which can be an ID for an agreement, widget, or library document. The REST API demarcates these as separate resources (cleaner design and strongly typed) and hence, based on the kind of resource you are working on, there is a corresponding /libraryDocuments, /widgets to these. Example: ``/widgets/{widgetId}, GET`` will getDocumentInfo for ``widgetId``, and similarly for documents, audit trail, etc.  
|   \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getDocumentInfosByExternalId <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#getDocumentInfosByExternalId>`__ \| `/agreements, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/getAgreements>`__ query = externalId \|

| ``externalId`` can be used to map your internal IDs to Adobe Sign IDs.  
|   \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getDocuments <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#getDocuments>`__ \| `/agreements/{agrId}/documents, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/getAllDocuments>`__ \|

| REST returns a list of document IDs that can be provided to the following endpoint to get a document stream.  
|   \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getDocumentUrls <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#getDocumentUrls>`__ \| `/agreements/{agrId}/combinedDocument/url, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/getCombinedDocumentUrl>`__ \|

| Retrieve the URL of the **combined document**.  
|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getDocumentUrls <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#getDocumentUrls>`__ \| `/agreements/{agrId}/documents/{docId}/url, GET <https://secure.na1.echosign.com/public/docs/restapi/v5#!/agreements/getDocumentUrl>`__ \|

| Retrieve the URL of an **individual document**.  
|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getDocumentImageUrls <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#getDocumentImageUrls>`__ \| `/agreements/{agrId}/documents/imageUrls, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/getAllDocumentsImageUrls>`__ \|

| Retrieve the image URLs of **all visible pages** of an agreement.  
|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getDocumentImageUrls <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#getDocumentImageUrls>`__ \| `/agreements/{agrId}/documents/{docId}/imageUrls, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/getDocumentImageUrls>`__ \|

| Retrieve image URLs of a specified documentID.  
|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getSupportingDocuments <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#getSupportingDocuments>`__ \| `/agreements/{agrId}/documents, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/getAllDocuments>`__ \|

| Can also specify the content format.  
|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getFormData <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#getFormData>`__ \| `/agreements/{agrId}/formData, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/getFormData>`__ \|

| Returns a CSV file stream.  
|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getAuditTrail <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#getAuditTrail>`__ \| `/agreements/{agrId}/auditTrail, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/getAuditTrail>`__ \|

|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getSigningUrl <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#getSigningUrl>`__ \| `/agreements/{agrId}/signingUrls, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/getSigningUrl>`__ \|

|  
|   ## User Methods: \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `createUser <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService19#createUser>`__ \| **v5 REST Only** `/users, POST <https://secure.na1.echosign.com/public/docs/restapi/v5#!/users/createUser>`__ \|

  \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `verifyUser <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#verifyUser>`__ \| `/users/{userId}, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/users/getUserDetail>`__\ \|

The REST equivalent can be used to see if the user exists, but does not support password verification.

  \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `searchUserDocuments <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#searchUserDocuments>`__ \| TBD \|

  \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getDocumentEventsForUser <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#getDocumentEventsForUser>`__ \| `/agreement/{agrId}/events, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/getEvents>`__ \|

  \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getEmbeddedView <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#getEmbeddedView>`__ \| `/agreements/{agrId}/views, POST <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/createAgreementView>`__ \|

Use the name = DOCUMENT to get the embedded view of an agreement.

|  
|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getUserDocuments <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#getUserDocuments>`__ \| `/agreements, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/getAgreements>`__ \|

|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getMyDocuments <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#getMyDocuments>`__ \| `/agreements, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/getAgreements>`__ \|

Use ``x-api-user`` for specifying the user whose agreements are to be retrieved.

|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getLibraryDocumentsForUser <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#getLibraryDocumentsForUser>`__ \| `/libraryDocuments, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/libraryDocuments/getLibraryDocuments>`__ \|

|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getMyLibraryDocuments <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#getMyLibraryDocuments>`__ \| `/libraryDocuments, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/libraryDocuments/getLibraryDocuments>`__ \|

Use ``x-api-user`` for specifying the user whose library documents are to be retrieved.

    \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getWidgetsForUser <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#getWidgetsForUser>`__ \| `/widgets, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/widgets/getWidgets>`__ \|

|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getMyWidgets <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#getMyWidgets>`__ \| `/widgets, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/widgets/getWidgets>`__ \|

| Use ``x-api-user`` for specifying the user whose widgets are to be retrieved.  
|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getMegaSignDocument <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#getMegaSignDocument>`__ \| `/megaSigns/{megaSignId}/agreements, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/megaSigns/getMegaSignChildAgreements>`__ \|

| Get all child agreement IDs of the parent MegaSign.  
|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getUsersInAccount <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#getUsersInAccount>`__ \| `/users, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/users/getUsers>`__ \|

|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `createGroup <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#createGroup>`__ \| **v5 REST Only** `/groups, POST <https://secure.na1.echosign.com/public/docs/restapi/v5#!/groups/createGroup>`__ \|

|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `deleteGroup <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#deleteGroup>`__ \| **v5 REST Only** `/groups/groupId, DELETE <https://secure.na1.echosign.com/public/docs/restapi/v5#!/groups/deleteGroup>`__ \|

|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `renameGroup <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#renameGroup>`__ \| **v5 REST Only** `/groups/{groupId}, PUT <https://secure.na1.echosign.com/public/docs/restapi/v5#!/groups/modifyGroup>`__ \|

|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getGroupsInAccount <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#getGroupsInAccount>`__ \| `/groups, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/groups/getGroups>`__ \|

|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getUsersInGroups <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#getUsersInGroup>`__ \| `/groups/{groupId}/users, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/groups/getUsersInGroup>`__ \|

|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `moveUsersToGroup <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#moveUsersToGroup>`__ \| `/users/{userId}/groups, PUT <https://secure.na1.echosign.com/public/docs/restapi/v6#!/users/updateGroupsOfUser>`__ \|

| Specify the new ``groupId`` in the request.  
|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getUserInfo <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#getUserInfo>`__ \| `/users/{userId}, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/users/getUserDetail>`__ \|

|     ## Web Form Methods:
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `createEmbeddedWidget <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#createEmbeddedWidget>`__ \| `/widgets, POST <https://secure.na1.echosign.com/public/docs/restapi/v6#!/widgets/createWidget>`__ \|

  \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `createPersonalEmbeddedWidget <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#createPersonalEmbeddedWidget>`__ \| **v5 REST Only** `/widgets/{widgetId}/personalize, PUT <https://secure.na1.echosign.com/public/docs/restapi/v5#!/widgets/updateWidgetPersonalize>`__ \|

  \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `personalizeEmbeddedWidget <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#personalizeEmbeddedWidget>`__ \| `/widgets, POST <https://secure.na1.echosign.com/public/docs/restapi/v6#!/widgets/createWidget>`__ \|

|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `createUrlWidget <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#createUrlWidget>`__ \| `/widgets, POST <https://secure.na1.echosign.com/public/docs/restapi/v6#!/widgets/createWidget>`__ \|

|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `createPersonalUrlWidget <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#createPersonalUrlWidget>`__ \| **v5 REST Only** `/widgets/{widgetId}/personalize, PUT <https://secure.na1.echosign.com/public/docs/restapi/v5#!/widgets/updateWidgetPersonalize>`__ \|

|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `personalizeUrlWidget <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#personalizeUrlWidget>`__ \| `/widgets, POST <https://secure.na1.echosign.com/public/docs/restapi/v6#!/widgets/createWidget>`__ \|

|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `disableWidget <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#disableWidget>`__ \| `/widgets/{widgetId}/state, PUT <https://secure.na1.echosign.com/public/docs/restapi/v6#!/widgets/updateWidgetState>`__ \|

| Use status value as ``INACTIVE``.  
|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `enableWidget <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#enableWidget>`__ \| `/widgets/{widgetId}/state, PUT <https://secure.na1.echosign.com/public/docs/restapi/v6#!/widgets/updateWidgetState>`__ \|

Use status value as ``ACTIVE``.

|  
|  

+---------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------+
| **SOAP Endpoint**                                                                                                               | **REST Endpoint**                                                                                  |
+=================================================================================================================================+====================================================================================================+
| `personalizeEmbeddedWidget <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService19#personalizeEmbeddedWidget>`__ | `/widgets, POST <https://secure.na1.echosign.com/public/docs/restapi/v6#!/widgets/createWidget>`__ |
+---------------------------------------------------------------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------+

|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `personalizeUrlWidget <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService19#personalizeUrlWidget>`__ \| `/widgets, POST <https://secure.na1.echosign.com/public/docs/restapi/v6#!/widgets/createWidget>`__\ \|

|  
|   ## Test Methods: \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `testPing <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#testPing>`__ \| `/baseURIs, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/baseUris/getBaseUris>`__ \|

|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `testEchoFile <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService22#testEchoFile>`__ \| TBD \|

|  
|   ## Deprecated Methods from legacy SOAP versions: ### Access Methods: \* issueAccessToken - `OAuth has replaced access tokens <https://www.adobe.io/apis/documentcloud/sign/docs.html#!adobedocs/adobe-sign/master/gstarted/configure_oauth.md>`__.

  ### Document Methods: \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `initiateInteractiveSendDocument <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService13#initiateInteractiveSendDocument>`__ \| `/agreements/{agrId}/views, POST <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/createAgreementView>`__ \|

  ### Status Methods: \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getDocumentUrlByVersion <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService13#getDocumentUrlByVersion>`__ \| `/agreement/{agreementID}/combinedDocument/url, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/getCombinedDocumentUrl>`__ \|

|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getDocumentByVersion <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService13#getDocumentByVersion>`__ \| `/agreements/{agreementId}/combinedDocument, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/getCombinedDocument>`__ \|

|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getImagesByVersion <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService13#getImagesByVersion>`__ \| `/agreements/{agrId}/documents/imageUrls, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/getAllDocumentsImageUrls>`__ \|

|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getLatestDocument <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService13#getLatestDocument>`__ \| `/agreements/{agrId}/documents, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/getAllDocuments>`__ \|

  \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getLatestDocumentUrl <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService13#getLatestDocumentUrl>`__ \| `/agreements/{agrId}/documents/{docId}/url, GET <>`__\ \ `/agreements/{agrId}/combinedDocument/url, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/getCombinedDocumentUrl>`__ \|

|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getLatestImages <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService13#getLatestImages>`__ \| `/agreements/{agrId}/documents/imageUrls, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/getAllDocumentsImageUrls>`__\ \ `/agreements/{agrId}/documents/{docId}/imageUrls, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/getDocumentImageUrls>`__ \|

|  
| ### User Methods: \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `getDocumentsForUser <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService13#getDocumentsForUser>`__ \| `/agreements, GET <https://secure.na1.echosign.com/public/docs/restapi/v6#!/agreements/getAgreements>`__ \|

|  
| \| **SOAP Endpoint** \| **REST Endpoint** \| \| :— \| :—- \| \| `createAccount <https://secure.na1.echosign.com/public/docs/EchoSignDocumentService19#createAccount>`__ \| None \|
