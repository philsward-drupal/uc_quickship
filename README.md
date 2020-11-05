# UC Quick Ship

## COMPATIBILITY

Drupal 7.x Ubercart 3.x

## ABOUT

Ubercart Quick Ship adds a single UI for creating packages and adding tracking numbers to the orders workflow.

The products are grouped by the ship from address setup on the product, then you group them by the carrier.

It uses the backend package system already built into Drupal and adds a GUI wrapper to make it a lot easier to deal with. It was designed around a dropship website where no actual labels are generated at the time of checkout and tracking must be entered manually at the time of package creation.

It also pairs with [uc_customtokens](https://github.com/philsward/uc_customtokens) by adding tracking related tokens that can be exposed elsewhere such as Rules for email templates.

## INSTALLATION

Install as usual in the sites/all/modules folder

## CONFIGURATION

Menu: Home » Administration » Store » Configuration » Orders

Settings: /admin/store/settings/orders/quickship

## USAGE

**Settings**  
The Settings page allows you to add a key|value list of carrier tracking URL's. see [carrier_list.md](https://github.com/philsward/uc_quickship/blob/main/carrier_list.md) for examples

Also on the settings page, you can add the machine name to a custom text list field that can be used for adding a radio button style field to the product where you set the name of the carrier that corresponds with the **key**|value. This allows you to specify the default carrier for a particular product in QuickShip.

For example, if you want UPS you would do:  

*product field*  
UPS|United Parcel Service

*quickship settings*  
UPS|https://wwwapps.ups.com/WebTracking/processRequest?&tracknum=@tracking_number

Notice how **UPS** match for the key

**Workflow**  
To use QuickShip, simply navigate to an order and click the **QuickShip** tab.

Products are first grouped by Product Pickup Address, then grouped by the carrier "if" set in the settings with each different carrier creating a new "shipment".

**Ship Date** and **Delivery Date** are not required. They can be exposed as tokens though for email templates and they are purely there for additional information to the customer to help reduce potential phone calls. This info is usually avaialble through the carrier at the time of tracking generation.

**Tracking Number** is pretty self explanatory. Paste the tracking number and save the form.

**Saving**  
The form will let you save, without being fully filled out. Simply click the [Create shipments] button when ready.  
Let's say you have two products with two tracking numbers, but only one number is availble. Add it to the respective shipment and click [Create shipments], then come back later and add the next one.

Completion of a package is determined by the color of the shipment group.  
* Red = No shipments have tracking numbers
* Yellow = Shipment does not have a tracking number
* Green = Shipment has a tracking number
