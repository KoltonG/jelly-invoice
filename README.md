# Jelly Invoice

<a href="http://jekyllrb.com/" target="_blank">Jekyll</a> Based Invoice generator for designer/developer freelancers who want a fully customizable and brandable, efficient solution to generating invoices.


## Launch Jelly
1. Download Jelly
2. Open Terminal, enter: 
3. `gem install jekyll` (If fails: try "sudo gem install jekyll")
4. `cd path/to/jelly/folder`
5. `jekyll serve --watch`
6. Slap the generated sever address in a browser
![Launching Jelly, Terminal step-by-step view](https://raw.githubusercontent.com/MRurka/jelly-invoice/gh-pages/img/terminal-example.jpg)


## Personalize Jelly
- Change the `logo.png` image in the img folder. 
- Populate the `_config.yml` file with your info. Changes to the `_config.yml` file require a fresh compile to update (re-do step 3, above).

``` yaml
# Site settings
title: Jelly invoice
baseurl: "/jelly-invoice" # the subpath of your site, e.g. /blog.
url: "http://mrurka.github.io" # the base hostname & protocol for your site. 

# Business Info
business-name: "Jelly Invoice Inc."
billing-address: "Name <br>555 Infinite Drive <br>ON, Canada <br>BN: RUD3-551991"

# Other
tax-amount: 0.13
tax-label: Tax
```


## Create an invoice
- Create a new file in the `_posts` directory. Name of file must follow format: `YEAR-MONTH-DAY-title.MARKUP`. Example: `2015-05-19-Special-Invoice-AB1234.markup`. See example files in folder.

**Reference list of default configurables for your invoice**
``` yaml
---

layout: hourly _or_ fixed # hourly means the "rate:" AND "hours:" configurables will need values. See them just below.
date: 2015-11-26 # must be YYYY-MM-DD
tags: 2015 # the invoice year
client-username: GoogleInc # must be a valid username found in one of the client profiles. See next section (Create client profiles).

title: Apple Watch iOS Design # title of your invoice
invoice-number: 001-RU-20150412 # however you personally number your invoices.
rate: 125 # Only necessary if the "layout:" value is "hourly" 

item_X: Website Design # Title of the item(s)
hours_X: 12 # Necessary only if the "layout:" value is "hourly"
price_X: 50 # Necessary only if the "layout:" value is "fixed"

---
```

## Create client profiles
What? Why? So you won't have to re-enter client info per invoice. One time deal.
- Create a new `.yml` file in the `_data/clients` directory. See below and example files in folder.
``` yaml
username: google
name: Google Incorporated
billing: "Google Incorporated <br>111 Richmond St W, <br>Toronto, Ontario, <br>Canada, M5H 2G4"
```


# Want to help?
- JS: Prices need to display with commas and 2 decimal rounded (e.g. $1,500.00). Currently, only the decimals work.






