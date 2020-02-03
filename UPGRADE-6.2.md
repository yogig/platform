UPGRADE FROM 6.1.x to 6.2
=======================

Core
----


Administration
--------------

* `sw-settings-custom-field-set`
    - Removed method which overrides the mixin method `getList`, use the computed `listingCriteria` instead
    - Add computed property `listingCriteria`
* `sw-settings-document-list`
    - Removed method which overrides the mixin method `getList`, use the computed `listingCriteria` instead
    - Add computed property `listingCriteria`
* Refactor  `sw-settings-snippet-list`
    - Removed `StateDeprecated`
    - Remove computed property `snippetSetStore`, use `snippetSetRepository' instead
    - Add computed property `snippetSetRepository`
    - Add computed property `snippetSetCriteria`
* Refactor `sw-settings-snippet-set-list`
    - Remove `StateDeprecated`
    - Remove computed property `snippetSetStore`, use `snippetSetRepository' instead
    - Add computed property `snippetSetCriteria`
    - The method `onConfirmClone` is now an asynchronous method
* Refactor mixin `sw-settings-list.mixin`
    - Remove `StateDeprecated`
    - Remove computed property `store`, use `entityRepository` instead
    - Add computed property `entityRepository`
    - Add computed property `listingCriteria`
* The component sw-plugin-box was refactored to use the "repositoryFactory" instead of "StateDeprecated" to fetch and save data
        - removed "StateDeprecated"
        - removed computed "pluginStore" use "pluginRepository" instead
* The component sw-settings-payment-detail was refactored to use the "repositoryFactory" instead of "StateDeprecated" to fetch and save data
    - removed "StateDeprecated"
    - removed computed "paymentMethodStore" use "paymentMethodRepository" instead
    - removed computed "ruleStore" use "ruleRepository" instead
    - removed computed "mediaStore" use "mediaRepository" instead
* Refactor the module `sw-settings-number-range-detail`
    * Remove LocalStore
    * Remove StateDeprecated
    * Remove data typeCriteria
    * Remove data numberRangeSalesChannelsStore
    * Remove data numberRangeSalesChannels
    * Remove data numberRangeSalesChannelsAssoc
    * Remove data salesChannelsTypeCriteria
    * Remove computed numberRangeStore use numberRangeRepository instead
    * Remove computed firstSalesChannel
    * Remove computed salesChannelAssociationStore
    * Remove computed numberRangeStateStore use numberRangeStateRepository instead
    * Remove computed salesChannelStore use salesChannelRepository instead
    * Remove computed numberRangeTypeStore use numberRangeTypeRepository instead
    * Remove method onChange
    * Remove method showOption
    * Remove method getPossibleSalesChannels
    * Remove method setSalesChannelCriteria
    * Remove method enrichAssocStores
    * Remove method onChangeSalesChannel
    * Remove method configHasSaleschannel
    * Remove method selectHasSaleschannel
    * Remove method undeleteSaleschannel


Storefront
----------

* We removed the SCSS skin import `@import 'skin/shopware/base'` inside `/Users/tberge/www/sw6/platform/src/Storefront/Resources/app/storefront/src/scss/base.scss`.
    * If you don't use the `@Storefront` bundle in your `theme.json` and you are importing the shopware core `base.scss` manually you have to import the shopware skin too in order to get the same result:

        Before
        ```
        @import "../../../../vendor/shopware/platform/src/Storefront/Resources/app/storefront/src/scss/base.scss";
        ```

        After
        ```
        @import "../../../../vendor/shopware/platform/src/Storefront/Resources/app/storefront/src/scss/base.scss";
        @import "../../../../vendor/shopware/platform/src/Storefront/Resources/app/storefront/src/scss/skin/shopware/base";