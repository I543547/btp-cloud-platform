<!-- loio4446ee47a04648668f1a4a604d08b0d2 -->

# Read Transport Log



<a name="loio4446ee47a04648668f1a4a604d08b0d2__section_y3t_354_bpb"/>

## Request

**URI:** /sap/opu/odata/sap/MANAGE\_GIT\_REPOSITORY/to\_Transport\_log

**Operation Type:** CRUD

**HTTP Method:**GET



### Request Headers

****


<table>
<tr>
<th valign="top">

Header

</th>
<th valign="top">

Required

</th>
<th valign="top">

Values

</th>
</tr>
<tr>
<td valign="top">

Accept

</td>
<td valign="top">

no

</td>
<td valign="top">

application/json

application/xml

</td>
</tr>
<tr>
<td valign="top">

x-csrf-token

</td>
<td valign="top">

no

</td>
<td valign="top">

fetch

</td>
</tr>
</table>



### Request Parameters

****


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Required

</th>
<th valign="top">

Data Type

</th>
<th valign="top">

Description

</th>
<th valign="top">

Parameter Type

</th>
</tr>
<tr>
<td valign="top">

uuid

</td>
<td valign="top">

yes

</td>
<td valign="top">

string

</td>
<td valign="top">

ID of the job

</td>
<td valign="top">

query string

</td>
</tr>
</table>



### Request Example

> ### Sample Code:  
> ```
> GET /sap/opu/odata/sap/MANAGE_GIT_REPOSITORY/Pull(uuid=02409ac8-dc6a-1edb-908e-31e4b44596d4’)/to_Transport_log HTTP/1.1
> 
> Host: host.com
> Authentication: basicAuthentication
> Accept: application/json
> 
> ```



<a name="loio4446ee47a04648668f1a4a604d08b0d2__section_tbd_zq4_bpb"/>

## Response



### Response Headers

****


<table>
<tr>
<th valign="top">

Header

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

x-csrf-token

</td>
<td valign="top">

Token, which can be used for POST requests

</td>
</tr>
</table>



### Response Status and Error Codes

****


<table>
<tr>
<th valign="top">

Code

</th>
<th valign="top">

Reason

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

OK

</td>
<td valign="top">

Read transport log succesfully

</td>
</tr>
<tr>
<td valign="top">

400

</td>
<td valign="top">

Bad Request

</td>
<td valign="top">

Could not find a transport log with the specified UUID.

</td>
</tr>
</table>



### Request Payload Example

> ### Sample Code:  
> ```
> { {
>     "d": {
>         "results": [ {
>             "__metadata": {
>                 "id": "host.com/sap/opu/odata/sap/MANAGE_GIT_REPOSITORY/ExecutionLogs(index_no=1m,uuid=guid'UUID')", "uri": "host.com/sap/opu/odata/sap/MANAGE_GIT_REPOSITORY/ExecutionLogs(index_no=1m,uuid=guid'UUID')", "type": "cds_sd_a4c_a2g_gha_sc_web_api.ExecutionLogsType"
>             }
>             ,
>             "index_no": "1",
>             "uuid": "UUID",
>             "type": "Information",
>             "descr": "Step X: Message",
>             "timestamp": "/Date(1571227438000+0000)/",
>             "criticality": 0,
>         }
>         ]
>     }
> }
> 
> ```

