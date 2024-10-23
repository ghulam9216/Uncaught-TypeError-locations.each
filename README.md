# Problem
Uncaught TypeError: locations.each is not a function in Magento admin showing occasionally on system configuration page in 2.4.5


# Solution

To resolve this issue, update the existing **system.js** file located at:

vendor/paypal/module-braintree-core/view/adminhtml/web/js/system.js


# Which Changes need in code

**Find this line of code**
   locations.each(function (loc) {

 **Replace by below code**

    $.each(locations, function (loc) {

**After this run the below commands**

Deploy static content (if necessary):
php bin/magento setup:upgrade
php bin/magento setup:static-content:deploy -f
php bin/magento setup:di:compile
php bin/magento cache:clean
php bin/magento cache:flush

# Compatibility
This fix is specifically form Magento 2.4.5. It may not be applicable to other versions of Magento without further testing.

# Contributing
If you encounter any issues or have suggestions for improvements, feel free to open an issue or submit a pull request.
