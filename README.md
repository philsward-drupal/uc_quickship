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

The Settings page allows you to add a key|value list of carrier tracking URL's
