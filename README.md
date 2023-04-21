# Superstore
A simple nostr webstore with whisper addresses for enhanced privacy

# What is this?

Superstore is a solution to this problem: I often wish I had a store where I could sell some stuff, but then I remember how hard it is to set up a store. First you need a server -- which probably costs money, unless you self host one, which is hard -- then you need to set up the store, which means naming it, styling it, adding payment methods, connecting a bank account or paypal or stripe or similar (and dealing with their fees), then add shipping options, then add your products, then -- assuming you want to accept bitcoin too -- you've probably got to install some special software or a special plugin or give custody to some third party. And you also lose your privacy because you're probably giving your xpubs to those folks too.

# What if there was a simpler way?

Nostr makes a lot of stuff that used to need a server not need one anymore. Or at least, you can often use a public nostr relay instead of a regular server. So I wondered if I could make a simple webstore that removes almost all of the hassles I've experienced in the past. So behold superstore:

- [x] It's hosted on github pages, which is free and easy
- [x] Or you can download the index.html file and run it locally, also free and easy
- [x] You don't need to name your store (you'll probably link to it on your blog or similar, so it will be associated with you that way)
- [x] You don't need to style it because it already looks great
- [ ] Ok that's a total lie, it looks like trash. Maybe I will add custom styling as a feature someday
- [x] You don't need to add a payment method -- we'll use bitcoin, which is free and easy
- [x] When you visit the store for the first time your browser autogenerates a nostr private key for you, which is free and easy
- [x] A bunch of bitcoin private keys will be derived from that nostr private key, which is free and easy
- [x] It uses my old [whisper addresses](https://github.com/supertestnet/whisper-addresses/) idea to preserve some of your privacy, which is free and easy
- [x] You just add products and shipping info and there is no other special software or plugins to run
- [x] It gives you a shareable link where anyone can visit your store, which is free and easy
- [x] It gives you a private link where you can manage your store, e.g. add more products or remove existing ones -- all free and easy
- [x] The built in bitcoin wallet is non-custodial and lets you withdraw your earnings whenever you want for free, and it's easy
- [x] If you notice an underlying theme here it's that running a store used to be costly and hard but this tool makes it free and easy

# How do I try it?

Just visit this link: https://supertestnet.github.io/superstore

There is no setup process for the store itself, you just immediately start adding products. When you're done you'll get a shareable link where anyone can view your store and a private link where you can manage your store and access your money.

Important! Save your private link. It contains your private key which you'll need to access your money and manage your store. If you lose your private key you lose your money. Keep it secret, keep it safe!

Also make sure you withdraw your money from the store frequently. The site uses whisper keys, which are sent to you in dms and not stored anywhere but on whatever relay you use. I personally don't trust nostr relays to store my dms forever so I recommend you withdraw your money quickly when you receive it, don't just let it sit there for weeks on end or the nostr relay you are connected to might delete your dms or go offline and leave you stranded without access to your money

# What are some upcoming features?

Not sure. Usually after I get a project to a state like this one is in I abandon it in favor of something else that's more exciting. But if I do keep at it I'd like to add these features:

- [ ] Better nostr connections -- about a third of the time when I load this page I don't actually get a connection to the nostr relay I use. It just sort of times out and an error message appears in my console. The user has no visiblity into this, the site just doesn't work (and if you're trying to view a store it just won't populate) which is super frustrating. It typically works when I refresh but I can automate that without refreshing the page so I should do that. (I should also add automatic reconnection logic in case the connection drops.)
- [ ] Better error handling -- sometimes mempool.space's api starts rate-limiting you, which causes errors, which can stop the page from running. Worst case scenario: you just paid for an order when the page crashes and you lose your money forever.
- [ ] Lightning support -- I can probably add this through submarine swaps but if I do it probably won't be very pretty, it will probably just confuse people because their wallet will say their payment is pending for a very long time while I wait for you to come online to finish the submarine swap
- [ ] Custom styling -- people like to make things look nice and feel like it's themed after their regular blog or website or whatever. Ok cool but visual flare isn't very important to me so maybe someone else can add code for that.
- [ ] Add custom relays -- there's no reason to have it limit you to just one hardcoded relay other than that's the easiest way to code this up. But soon I hope to add an option to set custom relays so you aren't limited to just one.
- [ ] Add more items to this upcoming features list -- yes, this is a meta feature, but I don't want to think about more stuff to add to this list so just write an issue so I can think about it ok?
