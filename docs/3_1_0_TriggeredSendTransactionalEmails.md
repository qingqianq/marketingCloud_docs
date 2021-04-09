<a name="Top"></a>
# marketing-cloud-connector



<a name="navlink"></a>
## 3.1 Triggered Send and Transactional Emails


**Important:** Make sure that your Marketing Cloud representative is aware that you intend to use Triggered Send functionality and Triggered Send Data Extension templates, and that you are connecting to Triggered Send using REST API. Have your representative ensure that the necessary permissions are turned on and enabled for your account. Enable these permissions for every Business Unit that you want to utilize with triggered sends.  

For each trigger: 

- The corresponding hook definition must be enabled in `CommunicationHandlers`. 
- The triggered send definition must be enabled in `MarketingCloudTriggers`.
- The trigger key is defined. 

To send attributes to Marketing Cloud, you must define a triggered email, typically with a data extension attached. Each data extension attribute is used for mapping subscriber attributes in the trigger definition. If a defined attribute doesn't exist on the Marketing Cloud side, Marketing Cloud ignores it.

In Marketing Cloud: 

1. Create a data extension from a template. 

	Each triggered send must connect to a **data extension**. the data extension can be shared if the data being stored overlaps between triggers.
	
	**Note:** Data extensions that collect triggering subscriber information must be built using a triggered-send-source data extension template.
	
	See [Create a Marketing Cloud Data Extension from a Template](https://help.marketingcloud.com/en/documentation/exacttarget/subscribers/data_extensions_for_exacttarget_marketing_cloud/creating_a_data_extension_from_a_template/).

2. Build a template-based email.

	Each triggered send requires an email. We recommended you create your email using Content Builder.  
	
	See [How to Build a Template Based Email Using the Classic Tools](https://help.marketingcloud.com/en/documentation/exacttarget/content/create_an_email/build_a_template_based_email/).

3. Create a triggered email message interaction.
	
	Associate the email and data extension that you created. We recommended enabling **Disable the Triggered Send when API errors are encountered**. 
	
	 See [Create a Triggered Email Message Interaction] (https://help.marketingcloud.com/en/documentation/exacttarget/interactions/triggered_emails/triggered_emails_guide/how_to_create_a_triggered_email_message_interaction/).
	 
4. Ensure your triggered send is in a running state, otherwise B2C Commerce can't use it.  

See [3.1.1 Triggered Send Configuration](3_1_1_MCConnectorInstallation-TriggeredSendConfiguration.md#navlink) for additional information.  

- - -

[Back to the top](#Top)