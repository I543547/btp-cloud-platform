<!-- loio9563ec60a6804dc68410a861dc605927 -->

# Determining the SI Unit

Use method `SI_UNIT_GET` to determine the SI unit.



<a name="loio9563ec60a6804dc68410a861dc605927__section_mmp_djm_rlb"/>

## Import Parameters

****


<table>
<tr>
<th valign="top">

Parameter Name

</th>
<th valign="top">

Value Help

</th>
</tr>
<tr>
<td valign="top">

DIMENSION

</td>
<td valign="top">

Dimension key

</td>
</tr>
<tr>
<td valign="top">

UNIT

</td>
<td valign="top">

Unit of measurement

</td>
</tr>
</table>



<a name="loio9563ec60a6804dc68410a861dc605927__section_en3_njm_rlb"/>

## Export Parameters

****


<table>
<tr>
<th valign="top">

Parameter Name

</th>
<th valign="top">

Value Help

</th>
</tr>
<tr>
<td valign="top">

SI\_UNIT

</td>
<td valign="top">

Base unit/SI unit of a dimension

</td>
</tr>
</table>



<a name="loio9563ec60a6804dc68410a861dc605927__section_enf_sjm_rlb"/>

## Exceptions

****


<table>
<tr>
<th valign="top">

Exception Name

</th>
<th valign="top">

Value Help

</th>
</tr>
<tr>
<td valign="top">

DIMENSION\_NOT\_FOUND

</td>
<td valign="top">

Dimension is not defined

</td>
</tr>
<tr>
<td valign="top">

UNIT\_NOT\_FOUND

</td>
<td valign="top">

Unit of measurement is not maintained

</td>
</tr>
<tr>
<td valign="top">

SI\_UNIT\_NOT\_FOUND

</td>
<td valign="top">

SI unit is not defined

</td>
</tr>
</table>

> ### Sample Code:  
> ```abap
> CLASS zcl_uom_conversion DEFINITION
>   PUBLIC
>   FINAL
>   CREATE PUBLIC .
> 
>   PUBLIC SECTION.
>      INTERFACES if_oo_adt_classrun.
>   PROTECTED SECTION.
>   PRIVATE SECTION.
> ENDCLASS.
> 
> CLASS zcl_uom_conversion IMPLEMENTATION.
> 
>   METHOD if_oo_adt_classrun~main.
> 
>    data: lo_unit type ref to cl_uom_conversion,
>          si_unit type cl_uom_conversion=>ty_msehi.
> 
>    lo_unit = cl_uom_conversion=>create( ).
> 
>    lo_unit->si_unit_get(
>      EXPORTING
>        dimension           = 'MASS'
>        unit                = 'G'
>      IMPORTING
>        si_unit             = si_unit
>      EXCEPTIONS
>        dimension_not_found = 1
>        unit_not_found      = 2
>        si_unit_not_found   = 3
>        others              = 4
>    ).
>    IF SY-SUBRC = 0.
>       out->write( si_unit ).
>    ENDIF.
> 
>   ENDMETHOD.
> 
> ENDCLASS.
> ```

