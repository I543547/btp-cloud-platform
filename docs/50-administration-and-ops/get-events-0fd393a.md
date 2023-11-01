<!-- loio0fd393a7691148c4930b9dd71235cb34 -->

# Get Events

Get all events associated with administrative operations in your accounts.



The events you get depend on the scopes you used to access the API.

To learn more about the scopes, see [SAP Cloud Management Service - Service Plans](sap-cloud-management-service-service-plans-a508b72.md).



<a name="loio0fd393a7691148c4930b9dd71235cb34__section_u3x_y3k_2mb"/>

## Prerequisites

You have obtained an access token with the `$XSAPPNAME.event.read` scope.



<a name="loio0fd393a7691148c4930b9dd71235cb34__section_nt4_ryj_mjb"/>

## Request

**URI:** <code>https://events-service.<i class="varname">&lt;app domain&gt;</i>.<i class="varname">&lt;landscape domain&gt;</i>/cloud-management/v1/events</code>

**HTTP Method:** *GET*



### Query Parameters


<table>
<tr>
<th valign="top">

Parameter Name

</th>
<th valign="top">

Required

</th>
<th valign="top">

Parameter Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`entityId`

</td>
<td valign="top">

No

</td>
<td valign="top">

Array of strings

</td>
<td valign="top">

The ID of the entity associated with the event.

</td>
</tr>
<tr>
<td valign="top">

`entityType`

</td>
<td valign="top">

No

</td>
<td valign="top">

Array of strings

</td>
<td valign="top">

The type of entity associated with the event.

For example Subaccount, Directory, or Tenant.

</td>
</tr>
<tr>
<td valign="top">

`eventType`

</td>
<td valign="top">

No

</td>
<td valign="top">

Array of strings

</td>
<td valign="top">

The type of the event that was triggered.

There are two groups of event types, Central Events and Local Events group.

The group you get depends on the scopes granted to you after you authorized to use the API.

You can query any event listed in the group that is relevant for your scope.

To retrieve all available event types, use the Event Types API.

See [Get Event Types](get-event-types-61b71bf.md).

The examples of some of the events for both groups:

-   **Central Events group:** GlobalAccount\_Update, AccountDirectory\_Creation, AccountDirectory\_Update, AccountDirectory\_Update\_Type, AccountDirectory\_Deletion, Subaccount\_Creation, Subaccount\_Deletion, Subaccount\_Update, Subaccount\_Move, AccountDirectoryTenant\_Creation, AccountDirectoryTenant\_Deletion, GlobalAccountEntitlements\_Update, EntityEntitlements\_Update, EntityEntitlements\_Move

-   **Local Events group:** SubaccountAppSubscription\_Creation, SubaccountAppSubscription\_Deletion, SubaccountAppSubscription\_Update, AppRegistration\_Creation, AppRegistration\_Deletion, AppRegistration\_Update, SubaccountTenant\_Creation, SubaccountTenant\_Update, SubaccountTenant\_Deletion, EnvironmentInstance\_Creation, EnvironmentInstance\_Deletion, EnvironmentInstances\_Deletion




</td>
</tr>
<tr>
<td valign="top">

`fromActionTime`

</td>
<td valign="top">

No

</td>
<td valign="top">

Integer

</td>
<td valign="top">

Start date and time to query the events by the action that triggered them.

Use the Unix epoch time in milliseconds \(you can find an online converter from a regular date-time format to the Unix epoch time format\).

> ### Example:  
> Monday, June 1, 2020 9:40:22 AM is 1590993622000 in Unix epoch milliseconds time.



</td>
</tr>
<tr>
<td valign="top">

`fromCreationTime`

</td>
<td valign="top">

No

</td>
<td valign="top">

Integer

</td>
<td valign="top">

Start date and time to query the events by when they were created.

Use the Unix epoch time in milliseconds \(you can find an online converter from a regular date-time format to the Unix epoch time format\).

> ### Example:  
> Monday, June 10, 2020 04:32:22 AM is 1591752742000 in Unix epoch milliseconds time.



</td>
</tr>
<tr>
<td valign="top">

`id`

</td>
<td valign="top">

No

</td>
<td valign="top">

Array of integers

</td>
<td valign="top">

The ID of the event.

</td>
</tr>
<tr>
<td valign="top">

`pageNum`

</td>
<td valign="top">

No

</td>
<td valign="top">

Integer

</td>
<td valign="top">

The page number to retrieve.

</td>
</tr>
<tr>
<td valign="top">

`pageSize`

</td>
<td valign="top">

No

</td>
<td valign="top">

Integer

</td>
<td valign="top">

The number of events to retrieve per page \(max = 150\).

</td>
</tr>
<tr>
<td valign="top">

`searchParams`

</td>
<td valign="top">

No

</td>
<td valign="top">

JSON Object

</td>
<td valign="top">

Additional search parameters that depend on the type of the events.

</td>
</tr>
<tr>
<td valign="top">

`sortField`

</td>
<td valign="top">

No

</td>
<td valign="top">

String

</td>
<td valign="top">

Field by which to sort the events.

</td>
</tr>
<tr>
<td valign="top">

`sortOrder`

</td>
<td valign="top">

No

</td>
<td valign="top">

String

</td>
<td valign="top">

Sort order for the events.

Can be ascending or descending.

Available values: `ASC`,`DESC`.

</td>
</tr>
<tr>
<td valign="top">

`toActionTime`

</td>
<td valign="top">

No

</td>
<td valign="top">

Integer

</td>
<td valign="top">

End date and time to query the events by the action that triggered them.

Use the Unix epoch time in milliseconds \(you can find an online converter from a regular date-time format to the Unix epoch time format\).

> ### Example:  
> Monday, June 4, 2020 11:40:22 AM is 1591260022000 in Unix epoch milliseconds time.



</td>
</tr>
<tr>
<td valign="top">

`toCreationTime`

</td>
<td valign="top">

No

</td>
<td valign="top">

Integer

</td>
<td valign="top">

End date and time to query the events by when they were created.

Use the Unix epoch time in milliseconds \(you can find an online converter from a regular date-time format to the Unix epoch time format\).

> ### Example:  
> Monday, June 6, 2020 12:32:22 AM is 1591392742000 in Unix epoch milliseconds time.



</td>
</tr>
</table>



<a name="loio0fd393a7691148c4930b9dd71235cb34__section_bgz_3fk_mjb"/>

## Response

Returns the list of events, and its associated objects.

**Content Type:***JSON*



### Response Status and Error Codes


<table>
<tr>
<th valign="top">

Code

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

200

</td>
<td valign="top">

Found events \(OK\)

</td>
</tr>
<tr>
<td valign="top">

400

</td>
<td valign="top">

Bad Request

Possible reasons:

-   The requested event type doesn’t belong to the events group associated with the scope you used to access the API

-   Requested event type is unknown

-   Query arguments are invalid




</td>
</tr>
<tr>
<td valign="top">

401

</td>
<td valign="top">

Unauthorized

Possible reasons:

-   Invalid token

-   A token with the scopes for central region was used to access the Events APIs in a local region.




</td>
</tr>
<tr>
<td valign="top">

403

</td>
<td valign="top">

Forbidden

</td>
</tr>
<tr>
<td valign="top">

404

</td>
<td valign="top">

Not Found

</td>
</tr>
<tr>
<td valign="top">

429

</td>
<td valign="top">

Rate Limit Exceeded

</td>
</tr>
<tr>
<td valign="top">

500

</td>
<td valign="top">

Internal Server Error

Possible reasons:

-   Failed to obtain global account or subaccount info




</td>
</tr>
</table>



### Response Objects and Their Parameters



### `BusinessEventsResponseCollection`

A collection of the event objects associated with the API call and the used scopes.


<table>
<tr>
<th valign="top">

Parameter Name

</th>
<th valign="top">

Parameter Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`events`

</td>
<td valign="top">

Array of JSON objects:

`BusinessEventResponseObject`

</td>
<td valign="top">

List of the event objects.

See the next table `BusinessEventResponseObject` for its parameters.

</td>
</tr>
<tr>
<td valign="top">

`morePages`

</td>
<td valign="top">

Boolean

</td>
<td valign="top">

Whether there are more pages with event objects to return.

</td>
</tr>
<tr>
<td valign="top">

`pageNum`

</td>
<td valign="top">

Integer

</td>
<td valign="top">

The current page number.

</td>
</tr>
<tr>
<td valign="top">

`total`

</td>
<td valign="top">

Integer

</td>
<td valign="top">

Total number of results.

</td>
</tr>
<tr>
<td valign="top">

`totalPages`

</td>
<td valign="top">

Integer

</td>
<td valign="top">

Total number of pages.

</td>
</tr>
</table>



### `BusinessEventResponseObject`

Includes details about an event in the list.


<table>
<tr>
<th valign="top">

Parameter Name

</th>
<th valign="top">

Parameter Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`actionTime`

</td>
<td valign="top">

String

</td>
<td valign="top">

The time the action triggered the event.

The format is Unix epoch time in milliseconds.

</td>
</tr>
<tr>
<td valign="top">

`creationTime`

</td>
<td valign="top">

String

</td>
<td valign="top">

The time the event record was created.

The format is Unix epoch time in milliseconds.

</td>
</tr>
<tr>
<td valign="top">

`details`

</td>
<td valign="top">

JSON object

</td>
<td valign="top">

Contains description and details about the requested events.

</td>
</tr>
<tr>
<td valign="top">

`entityId`

</td>
<td valign="top">

String

</td>
<td valign="top">

The ID of the entity associated with the event.

</td>
</tr>
<tr>
<td valign="top">

`entityType`

</td>
<td valign="top">

String

</td>
<td valign="top">

The type of the entity associated with the event.

</td>
</tr>
<tr>
<td valign="top">

`eventOrigin`

</td>
<td valign="top">

String

</td>
<td valign="top">

The service that reported the event.

</td>
</tr>
<tr>
<td valign="top">

`eventType`

</td>
<td valign="top">

String

</td>
<td valign="top">

The type of the event that was triggered.

There are two groups of event types: Local Events and Central Events group.

Only event types that belong to one of the groups is returned as the result of a single API call.

The event types group you get depends on the scope you used to access the API.

The examples of some of the events for both groups:

-   Central Events group: GlobalAccount\_Update, AccountDirectory\_Creation, AccountDirectory\_Update, AccountDirectory\_Update\_Type, AccountDirectory\_Deletion, Subaccount\_Creation, Subaccount\_Deletion, Subaccount\_Update, Subaccount\_Move, AccountDirectoryTenant\_Creation, AccountDirectoryTenant\_Deletion, GlobalAccountEntitlements\_Update, EntityEntitlements\_Update, EntityEntitlements\_Move

-   Local Events group: SubaccountAppSubscription\_Creation, SubaccountAppSubscription\_Deletion, SubaccountAppSubscription\_Update, AppRegistration\_Creation, AppRegistration\_Deletion, AppRegistration\_Update, SubaccountTenant\_Creation, SubaccountTenant\_Update, SubaccountTenant\_Deletion, EnvironmentInstance\_Creation, EnvironmentInstance\_Deletion, EnvironmentInstances\_Deletion




</td>
</tr>
<tr>
<td valign="top">

`globalAccountGUID`

</td>
<td valign="top">

String

</td>
<td valign="top">

The unique ID of the global account associated with the event.

</td>
</tr>
<tr>
<td valign="top">

`id`

</td>
<td valign="top">

Integer

</td>
<td valign="top">

The ID of the event.

</td>
</tr>
</table>



### Response Example

```
{
    "total": 3,
    "totalPages": 1,
    "pageNum": 0,
    "morePages": false,
    "events": [
        {
            "id": 584299,
            "actionTime": 1593494674668,
            "creationTime": 1593494674709,
            "details": {
                "description": "Subaccount created.",
                "guid": "6699b187-d17c-4783-bc8c-3263690d4aac",
                "parentGuid": "a7410cf4-84a5-46ac-9c15-52e34d283eb2",
                "displayName": "trial",
                "subaccountDescription": null,
                "region": "us10-staging",
                "jobLocation": null,
                "subdomain": "6a193bbetrial",
                "betaEnabled": false,
                "expiryDate": null
            },
            "globalAccountGUID": "a7410cf4-84a5-46ac-9c15-52e34d283eb2",
            "entityId": "6699b187-d17c-4783-bc8c-3263690d4aac",
            "entityType": "Subaccount",
            "eventOrigin": "accounts-service",
            "eventType": "Subaccount_Creation"
        },
        {
            "id": 584300,
            "actionTime": 1593494675583,
            "creationTime": 1593494676435,
            "details": {
                "description": "Addition and update of entitlements in a global account",
                "entitlementItems": {
                    "entitlements": [
                        {
                            "productId": "trial",
                            "name": "TRIAL",
                            "amount": 1,
                            "effectiveDate": null,
                            "allowedSubaccountIDs": null
                        }
                    ],
                    "origin": null
                }
            },
            "globalAccountGUID": "a7410cf4-84a5-46ac-9c15-52e34d283eb2",
            "entityId": "a7410cf4-84a5-46ac-9c15-52e34d283eb2",
            "entityType": "GlobalAccount",
            "eventOrigin": "entitlements-service",
            "eventType": "GlobalAccountEntitlements_Update"
        },
        {
            "id": 584315,
            "actionTime": 1593494726523,
            "creationTime": 1593494727151,
            "details": {
                "description": "Assignment of entitlements from global account to subaccount",
                "servicePlanAssignments": "{\"destinationlite\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":10,\"servicePlanAssignmentId\":21589}},\"serviceName\":\"destination\",\"servicePlanName\":\"lite\",\"servicePlanUniqueIdentifier\":\"destinationlite\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"mongodbmedium\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":1,\"servicePlanAssignmentId\":21590}},\"serviceName\":\"mongodb\",\"servicePlanName\":\"medium\",\"servicePlanUniqueIdentifier\":\"mongodbmedium\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"applicationruntime\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":100,\"servicePlanAssignmentId\":21591}},\"serviceName\":\"APPLICATION_RUNTIME\",\"servicePlanName\":\"MEMORY\",\"servicePlanUniqueIdentifier\":\"applicationruntime\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"cis-local\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":5,\"servicePlanAssignmentId\":21592}},\"serviceName\":\"cis\",\"servicePlanName\":\"local\",\"servicePlanUniqueIdentifier\":\"cis-local\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"html5-apps-repo-app-host\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":10,\"servicePlanAssignmentId\":21593}},\"serviceName\":\"html5-apps-repo\",\"servicePlanName\":\"app-host\",\"servicePlanUniqueIdentifier\":\"html5-apps-repo-app-host\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"rabbitmqsmall\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":1,\"servicePlanAssignmentId\":21594}},\"serviceName\":\"rabbitmq\",\"servicePlanName\":\"small\",\"servicePlanUniqueIdentifier\":\"rabbitmqsmall\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"rabbitmq-virtualhost\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":5,\"servicePlanAssignmentId\":21595}},\"serviceName\":\"rabbitmq\",\"servicePlanName\":\"virtualhost\",\"servicePlanUniqueIdentifier\":\"rabbitmq-virtualhost\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"postgresqlmedium\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":1,\"servicePlanAssignmentId\":21596}},\"serviceName\":\"postgresql\",\"servicePlanName\":\"medium\",\"servicePlanUniqueIdentifier\":\"postgresqlmedium\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"postgresqllarge\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":1,\"servicePlanAssignmentId\":21597}},\"serviceName\":\"postgresql\",\"servicePlanName\":\"large\",\"servicePlanUniqueIdentifier\":\"postgresqllarge\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"screeninghits-application\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":1,\"servicePlanAssignmentId\":21598}},\"serviceName\":\"screeninghits\",\"servicePlanName\":\"saas-application\",\"servicePlanUniqueIdentifier\":\"screeninghits-application\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"redis-dev\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":10,\"servicePlanAssignmentId\":21599}},\"serviceName\":\"redis\",\"servicePlanName\":\"dev\",\"servicePlanUniqueIdentifier\":\"redis-dev\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"redislarge\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":1,\"servicePlanAssignmentId\":21600}},\"serviceName\":\"redis\",\"servicePlanName\":\"large\",\"servicePlanUniqueIdentifier\":\"redislarge\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"rabbitmq-dev\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":10,\"servicePlanAssignmentId\":21601}},\"serviceName\":\"rabbitmq\",\"servicePlanName\":\"dev\",\"servicePlanUniqueIdentifier\":\"rabbitmq-dev\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"mongodblarge\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":1,\"servicePlanAssignmentId\":21602}},\"serviceName\":\"mongodb\",\"servicePlanName\":\"large\",\"servicePlanUniqueIdentifier\":\"mongodblarge\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"rabbitmqlarge\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":1,\"servicePlanAssignmentId\":21603}},\"serviceName\":\"rabbitmq\",\"servicePlanName\":\"large\",\"servicePlanUniqueIdentifier\":\"rabbitmqlarge\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"featureflagslite\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":10,\"servicePlanAssignmentId\":21604}},\"serviceName\":\"feature-flags\",\"servicePlanName\":\"lite\",\"servicePlanUniqueIdentifier\":\"featureflagslite\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"auditlog-viewer_standard_\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":10,\"servicePlanAssignmentId\":21605}},\"serviceName\":\"auditlog-viewer\",\"servicePlanName\":\"standard\",\"servicePlanUniqueIdentifier\":\"auditlog-viewer_standard_\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"redismedium\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":1,\"servicePlanAssignmentId\":21606}},\"serviceName\":\"redis\",\"servicePlanName\":\"medium\",\"servicePlanUniqueIdentifier\":\"redismedium\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"rabbitmqmedium\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":1,\"servicePlanAssignmentId\":21607}},\"serviceName\":\"rabbitmq\",\"servicePlanName\":\"medium\",\"servicePlanUniqueIdentifier\":\"rabbitmqmedium\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"postgresqlsmall\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":2147483647,\"servicePlanAssignmentId\":21608}},\"serviceName\":\"postgresql\",\"servicePlanName\":\"small\",\"servicePlanUniqueIdentifier\":\"postgresqlsmall\",\"isEntitlementUnlimited\":true,\"assignmentLevel\":\"SUBACCOUNT\"},\"mongodb_xsmall\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":1,\"servicePlanAssignmentId\":21609}},\"serviceName\":\"mongodb\",\"servicePlanName\":\"xsmall\",\"servicePlanUniqueIdentifier\":\"mongodb_xsmall\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"connectivitylite\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":10,\"servicePlanAssignmentId\":21610}},\"serviceName\":\"connectivity\",\"servicePlanName\":\"lite\",\"servicePlanUniqueIdentifier\":\"connectivitylite\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"rabbitmqxsmall\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":2147483647,\"servicePlanAssignmentId\":21611}},\"serviceName\":\"rabbitmq\",\"servicePlanName\":\"xsmall\",\"servicePlanUniqueIdentifier\":\"rabbitmqxsmall\",\"isEntitlementUnlimited\":true,\"assignmentLevel\":\"SUBACCOUNT\"},\"portalservicessite\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":10,\"servicePlanAssignmentId\":21612}},\"serviceName\":\"portal-services\",\"servicePlanName\":\"site\",\"servicePlanUniqueIdentifier\":\"portalservicessite\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"redisxsmall\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":1,\"servicePlanAssignmentId\":21613}},\"serviceName\":\"redis\",\"servicePlanName\":\"xsmall\",\"servicePlanUniqueIdentifier\":\"redisxsmall\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"mongodbsmall\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":1,\"servicePlanAssignmentId\":21614}},\"serviceName\":\"mongodb\",\"servicePlanName\":\"small\",\"servicePlanUniqueIdentifier\":\"mongodbsmall\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"redissmall\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":1,\"servicePlanAssignmentId\":21615}},\"serviceName\":\"redis\",\"servicePlanName\":\"small\",\"servicePlanUniqueIdentifier\":\"redissmall\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"postgresqlxsmall\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":1,\"servicePlanAssignmentId\":21616}},\"serviceName\":\"postgresql\",\"servicePlanName\":\"xsmall\",\"servicePlanUniqueIdentifier\":\"postgresqlxsmall\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"mongodb-dev-large\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":1,\"servicePlanAssignmentId\":21617}},\"serviceName\":\"mongodb\",\"servicePlanName\":\"dev-large\",\"servicePlanUniqueIdentifier\":\"mongodb-dev-large\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"screening-application\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":1,\"servicePlanAssignmentId\":21618}},\"serviceName\":\"screening\",\"servicePlanName\":\"saas-application\",\"servicePlanUniqueIdentifier\":\"screening-application\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"postgresql-dev\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":150,\"servicePlanAssignmentId\":21619}},\"serviceName\":\"postgresql\",\"servicePlanName\":\"dev\",\"servicePlanUniqueIdentifier\":\"postgresql-dev\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"sample-saas-app-i337243-test\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":1,\"servicePlanAssignmentId\":21620}},\"serviceName\":\"sample-saas-app-i337243\",\"servicePlanName\":\"test\",\"servicePlanUniqueIdentifier\":\"sample-saas-app-i337243-test\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"jobscheduler-standard\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":5,\"servicePlanAssignmentId\":21621}},\"serviceName\":\"jobscheduler\",\"servicePlanName\":\"standard\",\"servicePlanUniqueIdentifier\":\"jobscheduler-standard\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"},\"cis-central\":{\"decreased\":{},\"increased\":{\"6699b187-d17c-4783-bc8c-3263690d4aac\":{\"amount\":5,\"servicePlanAssignmentId\":21622}},\"serviceName\":\"cis\",\"servicePlanName\":\"central\",\"servicePlanUniqueIdentifier\":\"cis-central\",\"isEntitlementUnlimited\":false,\"assignmentLevel\":\"SUBACCOUNT\"}}",
                "subaccountIdToRegion": "{\"6699b187-d17c-4783-bc8c-3263690d4aac\":\"us10-staging\"}"
            },
            "globalAccountGUID": "a7410cf4-84a5-46ac-9c15-52e34d283eb2",
            "entityId": "a7410cf4-84a5-46ac-9c15-52e34d283eb2",
            "entityType": "GlobalAccount",
            "eventOrigin": "entitlements-service",
            "eventType": "SubaccountEntitlements_Update"
        }
    ]
}
```

**Related Information**  


[Getting an Access Token for SAP Cloud Management Service APIs](getting-an-access-token-for-sap-cloud-management-service-apis-3670474.md "The APIs of the SAP Cloud Management service for SAP BTP are protected with the OAuth 2.0 Password grant type and, in some cases, also the Client Credentials grant type. This procedure guides you through the steps to create an OAuth client and obtain an access token from SAP Authorization and Trust Management service (xsuaa) to call the APIs of the SAP Cloud Management service.")

[Using the Events Service APIs](using-the-events-service-apis-94e1895.md "The Events service provides REST APIs that collect information about events relating to account administrative operations in the microservices of the SAP Cloud Management service for SAP BTP, such as Accounts, Entitlements, Provisioning, and the SAP SaaS Provisioning service, within central and local regions.")

[Get Event Types](get-event-types-61b71bf.md "Get all available event types, including their categories and their available search parameters.")

