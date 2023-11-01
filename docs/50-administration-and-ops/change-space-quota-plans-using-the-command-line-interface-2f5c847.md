<!-- loio2f5c84760a8b433ea50434630560ad7a -->

# Change Space Quota Plans Using the Command Line Interface

Change space quota plans in the Cloud Foundry environment using the Cloud Foundry command line interface \(cf CLI\).



<a name="loio2f5c84760a8b433ea50434630560ad7a__prereq_rkm_h5m_qz"/>

## Prerequisites

-   You have the Org Manager role in the organization in which you'd like to change space quota plans. For more information about roles and permissions, see [https://docs.cloudfoundry.org/concepts/roles.html](https://docs.cloudfoundry.org/concepts/roles.html).
-   Download and install the cf CLI and log on to your Cloud Foundry instance. For more information, see [Download and Install Cloud Foundry Command Line Interface](https://help.sap.com/viewer/hcp_cf/4ef907afb1254e8286882a2bdef0edf4.html) and [Log On to the Cloud Foundry Environment Using the Cloud Foundry Command Line Interface](log-on-to-the-cloud-foundry-environment-using-the-cloud-foundry-command-line-interface-7a37d66.md).




<a name="loio2f5c84760a8b433ea50434630560ad7a__steps_kyg_xcn_qz"/>

## Procedure

1.  \(Optional\) Enter the following string to identify the names of all space quota plans available in your org:

    ```
    cf space-quotas
    ```

2.  To modify a quota plan, enter the following string:

    ```
    cf update-space-quota SPACE-QUOTA-NAME [-i MAX-INSTANCE-MEMORY] [-m MEMORY] [-n NEW_NAME] [-r ROUTES] [-s SERVICES] [--allow-paid-service-plans | --disallow-paid-service-plans]
    
    
    ```

    > ### Note:  
    > For more information about managing space quota plans, see [https://docs.cloudfoundry.org/adminguide/quota-plans.html\#space](https://docs.cloudfoundry.org/adminguide/quota-plans.html#space).


**Related Information**  


[Edit Space Quotas](edit-space-quotas-2a58364.md "Edit space quotas in the Cloud Foundry environment using the SAP BTP cockpit.")

[Configure Entitlements and Quotas for Subaccounts](configure-entitlements-and-quotas-for-subaccounts-5ba357b.md "Distribute the entitlements that are available in your global account by adding service plans and their allowed quotas to your subaccounts using the SAP BTP cockpit.")

[Managing Entitlements and Quotas Using the Cockpit](managing-entitlements-and-quotas-using-the-cockpit-c824874.md "When you purchase an enterprise account, you are entitled to use a specific set of resources, such as the amount of memory that can be allocated to your applications.")

