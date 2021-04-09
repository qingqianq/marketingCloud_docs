<a name="Top"></a>
# marketing-cloud-connector


## 2.1 Handler Framework Installation

The Handler Framework for the Marketing Cloud Connector cartridge introduces reusable integration points into the Commerce Cloud Reference Architecture (Storefront Reference Architecture (SFRA) or SiteGenesis). Managing integration points via B2C Commerce site configuration rather than applying custom code changes, lets you install more integrations without modifying numerous areas of the reference architecture. Instead of implementing these changes directly in the reference application, we moved the functionality to the utility cartridge to provide as much customization flexibility as possible while keeping both code bases separate.  

Currently supported through site configurations and preferences is the management of Communication Handlers.

Communication Handlers allow the granular definition of triggered/send email origins, such as B2C Commerce Reference Architecture or Marketing Cloud.


You can use the following email types  with either B2C Commerce or Marketing Cloud.

* Account - Created
* Account - Updated
* Account - Password Changed
* Account - Password Reset
* Account - Locked Out
* Customer Service - Contact Us
* Gift Certificate - Send Certificate
* Order - Confirmation


The installation instructions refer to the setup and implementation within a B2C Commerce environment (Business Manager and custom code repository). Knowledge of B2C Commerce code development techniques and tools are a prerequisite.

<a name="Installation"></a>
## Install the Handler Framework

1. Check out the latest tagged release in the  [Marketing Cloud Connector Repository](https://github.com/SalesforceCommerceCloud/marketing-cloud-connector).

2. Add the `int_handlerframework` and `modules` directories to your storefront repository cartridges directory, and upload the cartridges to your storefront instance.  Please note that there is a file called `synchronous-promise.js` which is included in this release, but is not within the `int_handlerframework` cartridge.  This file will need to be uploaded to the `modules` directory along with the other `modules` files.  The `synchronous-promise.js` file is located in the `cartridges` directory, parallel to the `int_handlerframework` directory.

    **NOTE**: If you already have a `modules` directory, merge the directory contents together.

3. Ensure that Business Manager loads the cartridge properly.

	To do so, activate a different code version (in Business Manager, go to **Administration > Site Development > Code Deployment**) and then reactivate your current code version. This ensures that the necessary job-step types are registered correctly, which is necessary before importing.

4. Import the metadata, custom objects, and jobs definitions into your B2C Commerce environment.

	XML definitions can be found in the [/site_template/ directory](https://github.com/SalesforceCommerceCloud/handler-framework/tree/develop/sites/site_template).

	The custom object definition for `CommunicationHandlers` is set to site-level, by default. This is to support the possibility of different configurations per site. If you plan on using the same configuration for your entire organization, you can change the site-level custom objects to organization-level custom objects.
To do so:
    1. Open `handler-framework/sites/site_template/meta/custom-objecttype-definitions.xml`.
    2. Change `<storage-scope>site</storage-scope>` to `<storage-scope>organization</storage-scope>`.
    3. Save, and import the definition file.

5. Update your site cartridge path:  `app_storefront_controllers:app_storefront_core:int_handlerframework`.

- - -

[Back to the top](#Top)
