<!-- loio3198c2ac3a11467686920c303d14df78 -->

# Pull

**Resource path:** /sap/opu/odata/sap/MANAGE\_GIT\_REPOSITORY/Pull



<a name="loio3198c2ac3a11467686920c303d14df78__section_zps_1q4_bpb"/>

## Operations



### CRUD Operations

****


<table>
<tr>
<th valign="top">

HTTP Method

</th>
<th valign="top">

Description

</th>
<th valign="top">

Operation

</th>
</tr>
<tr>
<td valign="top">

GET

</td>
<td valign="top">

Read pull

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

POST

</td>
<td valign="top">

Trigger a pull job

</td>
<td valign="top">

 

</td>
</tr>
</table>



### Custom Operations

****


<table>
<tr>
<th valign="top">

HTTP Method

</th>
<th valign="top">

Description

</th>
<th valign="top">

Operation

</th>
<th valign="top">

URI

</th>
</tr>
<tr>
<td valign="top">

GET

</td>
<td valign="top">

Associationl

</td>
<td valign="top">

 

</td>
<td valign="top">

/sap/opu/odata/sap/MANAGE\_GIT\_REPOSITORY /Pull\(guid’UUID’\)/to\_Executiong\_log

</td>
</tr>
<tr>
<td valign="top">

GET

</td>
<td valign="top">

Associationl

</td>
<td valign="top">

 

</td>
<td valign="top">

/sap/opu/odata/sap/MANAGE\_GIT\_REPOSITORY /Pull\(guid’UUID’\)/to\_Transport\_log

</td>
</tr>
</table>



### Parameters

****


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

uuid

</td>
<td valign="top">

ID of the job

</td>
</tr>
<tr>
<td valign="top">

sc\_name

</td>
<td valign="top">

Name of the software component

</td>
</tr>
<tr>
<td valign="top">

branch\_name

</td>
<td valign="top">

Name of the branch

</td>
</tr>
<tr>
<td valign="top">

commit\_id

</td>
<td valign="top">

Commit ID

</td>
</tr>
<tr>
<td valign="top">

import\_type

</td>
<td valign="top">

Type of import

</td>
</tr>
<tr>
<td valign="top">

status

</td>
<td valign="top">

Status of the job

</td>
</tr>
<tr>
<td valign="top">

status\_descr

</td>
<td valign="top">

Status description

</td>
</tr>
<tr>
<td valign="top">

user\_name

</td>
<td valign="top">

Name of the user who triggered the action

</td>
</tr>
<tr>
<td valign="top">

start\_time

</td>
<td valign="top">

Start time of the job

</td>
</tr>
<tr>
<td valign="top">

change\_time

</td>
<td valign="top">

Last update of the job

</td>
</tr>
</table>

