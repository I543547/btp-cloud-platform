<!-- copy21e27a355a154dd9acfa94e705eff82b -->

# Integrating Security Audit Logs

Service name: `RSAU_LOG_API`

This service enables you to retrieve the security audit log data. You can use the audit log data to integrate them into your Security and Event Management solution \(SIEM\) to detect security relevant event situations.

This is an OData version 4 service. This version aims to improve processing time and resource consumption of clients and servers. This includes a lightweight JSON format that reduces the size of every response.



<a name="copy21e27a355a154dd9acfa94e705eff82b__section_technical_details"/>

## Technical Details

A service group contains services belonging to the same business object model and so it shares similar environment conditions. This means the configuration and administration of a service group apply to all services in a service group, that is, routing, authorization, and so on, so you only have to do them once.

In the OData version 4 \(V4\) runtime implementation of the SAP Gateway Foundation, framework services originate from repositories.


<table>
<tr>
<th valign="top">

Service Group \(incl. Namespace if Existent\)

</th>
<th valign="top">

Repository ID

</th>
<th valign="top">

Service Name \(incl. Namespace if Existent\)

</th>
<th valign="top">

Version

</th>
</tr>
<tr>
<td valign="top">

`RSAU_LOG_API` 

</td>
<td valign="top">

`SRVD_A2X` 

</td>
<td valign="top">

`RSAU_LOG_API_SERVICE` 

</td>
<td valign="top">

`0001` 

</td>
</tr>
</table>



<a name="copy21e27a355a154dd9acfa94e705eff82b__section_service_structure"/>

## Service Structure

**Service Header \(optional\)**

The service header contains information about the service.

**Entities**

The entities contain the business data of the service.

****


<table>
<tr>
<th valign="top">

Entity

</th>
<th valign="top">

Description

</th>
<th valign="top">

Necessity

</th>
<th valign="top">

Link to Details

</th>
</tr>
<tr>
<td valign="top">

Security Audit Log

</td>
<td valign="top">

Security Audit Log

</td>
<td valign="top">

 

</td>
<td valign="top">

[Retrieving Security Audit Log](retrieving-security-audit-log-ce39470.md) 

</td>
</tr>
</table>



<a name="copy21e27a355a154dd9acfa94e705eff82b__section_service_response"/>

## Service Response

The details included in the response vary according to the type of operation. For more information, see Operation for Security Audit Log Integration.



<a name="copy21e27a355a154dd9acfa94e705eff82b__section_crs_psc_lwb"/>

## Integration with SIEM Solution

Service name: ***RSAU\_LOG\_API***

Communication scenario: ***SAP\_COM\_0750***

This service enables you to retrieve the security audit log data. You can use the audit log data to integrate them into your Security and Event Management solution \(SIEM\) to detect security relevant event situations.



<a name="copy21e27a355a154dd9acfa94e705eff82b__section_additional_information"/>

## Additional Information

> ### Note:  
> For more details about Communication Management, see [Communication Management](communication-management-2e84a10.md).

