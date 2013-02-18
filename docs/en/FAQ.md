# Frequently Asked Questions & Troubleshooting

If you have a common question needing a common answer, hopefully you can find it here.

*Also see the user documentation FAQ.*

### Which version of Silverstripe / shop / payment should I use?

Please refer to the requirements found at [ss-shop.org](http://ss-shop.org)

### How to customise forms - checkout, add product, cart, etc

If the form has been built well, it should have extension hooks that allow you to make
adjustments by writing your own Extension class.

### How do I customise the country field? - change country list, remove field completely, set default

see the [customising docs](Customising#CountryFeild)

### How do I set my site to use a different currency?

	Payment::set_site_currency('CUR'); //where 'CUR' is the currency code

### I can't get payments to work? eg: PayPal, PaymentExpress, Other..

see [payment](Payment)

### How do I add shipping calculation to the checkout process? How do I customise fees for different locations / delivery zones?

The default shop module provides a few shipping [modifiers](OrderModifiers). You can also have one custom built for your needs.

### How do I use in a different language?

Follow the [Silverstripe internationalisation guide](http://doc.silverstripe.org/sapphire/en/topics/i18n)
We welcome your contribution of language files.

### When are cart/order totals recalculated?

When changes are made to an order, the totals need to be recalculated. It is too expensive to do this on every
single change.

Totals are recalculated on every request for carts. The recalculation is triggered by the Cart function,
which is for use in templates only. It will only recalculate once, so make sure recalculation isn't triggered
early, producing incorrect results.

After an order is placed, recalculation will only occur on demand.