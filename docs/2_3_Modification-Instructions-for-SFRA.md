<a name="Top"></a>
# marketing-cloud-connector: 




<a name="navlink"></a>
## 2.3 SFRA Modification Instructions 
<a name="Overlay"></a>
### Using the SFRA Overlay Cartridge

The release of the Marketing Cloud Connector version 2.0.0, includes the _plugin\_marketing\_cloud_ cartridge.  This cartridge overlays the SFRA main cartridge (_app\_storefront\_base_) and replaces the functionality to activate the Marketing Cloud Connector hooks.  It contains all the changes the manual modifications instructions advise you to make. You still need to import and configure the metadata and custom objects, but you don't have to manually cut and paste all the code from these instructions into your SFRA.

After loading the _plugin\_marketing\_cloud_ cartridge, adjust your cartridge path to look like:
`plugin_marketing_cloud:app_storefront_base:int_marketing_cloud:int_handlerframework`

**Note:** These instructions apply only to Version 2.0.0 of the Marketing Cloud Connector after the merging of [Pull Request 27](https://github.com/SalesforceCommerceCloud/marketing-cloud-connector/pull/27).  If you're using a previous release, use the [Manual Modification Instructions](2_5_ManualModifications.md#navlink).

- - -

[Back to the top](#Top)