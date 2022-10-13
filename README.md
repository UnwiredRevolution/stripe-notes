#### Key Concepts

When I redirect a user to check out with Stripe I have to provide a Price. One or more Prices are associated with a Product. In our case the Products will be the subscription Tiers, and the prices will be the rates.
[Products and Prices](https://stripe.com/docs/products-prices/how-products-and-prices-work#what-is-a-price)
How subscriptions work in Stripe.
[Recurring Price Models](https://stripe.com/docs/products-prices/pricing-models)
More detail on how to design a subscription in Stripe.
[Design a Subscription Integration](https://stripe.com/docs/billing/subscriptions/designing-integration)
Information on how Stripe supports subscription changes. They have a process various scenarios, like pro-rating a yearly plan without changing the billing date, or what scenarios might require a billing date reset.
[Changing Subscriptions](https://stripe.com/docs/billing/subscriptions/change)
This is how Stripe supports usage-based billing. Their examples primarily focus on per-minute or per-request type scenarios. Per-user metered billing is harder to pin down (if that's what we used). We need a way to take a flat rate and multiply it by a number we can increment. So if you said we charged $0.05 per active device per day, then we could report a count of active devices each day and at the end of the month we'd have a total number of "device-days" that Stripe would multiply by the rate.
[Usage-based Billing](https://stripe.com/docs/billing/subscriptions/usage-based)

I don't know anything about how we manage invoices, but it seems like it's worth asking the question of whether we manage all our Ockettio invoices through Stripe, regardless of payment method.
[Invoices](https://stripe.com/docs/invoicing/overview)
This seemed like an interesting read if we were interested in driving all of our billing through Stripe.
[Sales-led Billing](https://stripe.com/docs/billing/subscriptions/sales-led-billing)
If we're planning on being available globally we'll have to worry about things like VAT (I guess??). Also my understanding is there are some different credit card verification standards elsewhere that we may need to support depending on how we implement our Stripe integration (how much we embed vs. let them host)
[Stripe Tax](https://stripe.com/docs/billing/taxes)

