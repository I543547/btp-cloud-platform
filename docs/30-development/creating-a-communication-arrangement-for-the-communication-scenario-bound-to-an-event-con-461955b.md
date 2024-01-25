<!-- loio461955b048e14b09b2422b1dfb66f1fb -->

# Creating a Communication Arrangement for the Communication Scenario bound to an Event Consumption Model

To be able to receive events from the event exchange infrastructure service instance, you must configure the inbound communication from the event exchange infrastructure to the consuming event consumption model.



## Prerequisites

-   You've set up a communication arrangement for`SAP_COM_0092` or `SAP_COM_0492` as described in [Communication Management](communication-management-659855d.md).

-   You've created an event consumption model and a *Communication Scenario* as described in [Event Consumption](event-consumption-a2c4285.md).




## Context

Following the procedure, you create an inbound communication arrangement.



## Procedure

1.  Log on to the SAP Fiori launchpad in the ABAP environment system.

2.  In the *Communication Management* app, select the *Communication Arrangements* artifact.

3.  Choose *New*.

4.  Select the *Communication Scenario* that was created for the respective event consumption model.

    You can recognize the scenario by its `Inbound Service`. An `Inbound Service` is created for each event consumption model and later on assigned to the respective communication scenario.

5.  Choose an *Arrangement Name* and click on *Create*.

6.  To assign a communication system, proceed as follows:

    -   Assign an existing communication system by selecting a *Communication System*. You can ignore the substeps.
    -   Create a communication system as described in [How to Create Communication Systems](https://help.sap.com/docs/btp/sap-business-technology-platform/how-to-create-communication-systems).

    1.  In the *General* tab under *Technical Data*, pull the switch for *Event Mesh* to *ON*.

        Note that communication arrangements created for an event consumption model only support inbound communication. That's why the *Inbound Only* flag is activated when switching *Event Mesh* on.

    2.  In the *General* tab under *Technical Data*, select the *Event Channel* that you've configured as described in [Communication Management](communication-management-659855d.md).

        The *Event Channel* name you see in the value help is the name that was assigned in the property *Channel* of the respective `SAP_COM_0092` or SAP\_COM\_0492 communication arrangement.

    3.  In the *Users for Inbound Communication* tab, add an inbound user.

        > ### Note:  
        > The *User for Inbound Communication* \(inbound user\) and the *Communication User* must be maintained as two different users. Make sure to create a dedicated inbound user, apart from your communication user. To create a new inbound user, follow the steps described in [How to Create Communication Users](https://help.sap.com/docs/btp/sap-business-technology-platform/how-to-create-communication-users).
        > 
        > The inbound user is used later for event processing. This user has authorizations maintained in the `Authorization Default Values` as described in [Adjusting the Generated Artifacts](https://help.sap.com/docs/SAP_S4HANA_CLOUD/25cf71e63940453397a32dc2b7676947/090230c1c26346518c5b82687ab2cd6f.html).

    4.  Choose *Save*.


    In general, you can assign multiple event consumption models via the corresponding communication scenarios to the same `SAP_COM_0092` or SAP\_COM\_0492 communication arrangement.




<a name="loio461955b048e14b09b2422b1dfb66f1fb__result_knv_5mz_xtb"/>

## Results

You've created an inbound communication arrangement for your event consumption model.

**Related Information**  


[How to Create a Communication Arrangement](https://help.sap.com/docs/btp/sap-business-technology-platform/how-to-create-communication-arrangement)

