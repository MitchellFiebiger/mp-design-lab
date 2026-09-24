MP DESIGN LAB — WEBSITE DRAFT
=============================

index.html is the entire site. One file, no build step, no dependencies.
Everything is inline except the Google Fonts link, which loads over the
internet. Double-click it to see it in a browser right now.


HOW TO PUT IT ONLINE
--------------------

Pick whichever is easiest. All three produce a working public URL.

1) FASTEST — Netlify Drop (about two minutes, free, no account to start)
   Go to https://app.netlify.com/drop and drag this whole folder onto the
   page. You get a live URL immediately. Good enough to share today.

2) GITHUB PAGES (free, good for the long term)
   - Make a new public repo
   - Upload index.html to the root of it
   - Settings > Pages > Source: "Deploy from a branch" > main > / (root)
   - Live in a minute or two at username.github.io/reponame

3) ANY NORMAL WEB HOST
   Upload index.html to the web root (public_html, www, htdocs — whatever
   your host calls it). It must be named index.html to load as the homepage.


POINTING mpdesignlab.com AT IT
------------------------------

The domain is registered at GoDaddy. Once the site is hosted somewhere,
go to GoDaddy > My Products > Domains > DNS and follow the host's custom
domain instructions (Netlify and GitHub Pages both walk you through it).
Netlify's is under Domain settings > Add custom domain.

NOTE: GoDaddy's Airo website builder cannot host this file as-is. It's a
site builder, not a file host. If you want to stay on Airo, rebuild the
sections in their editor using this page as the reference for the copy and
the order — don't try to paste the HTML in.


BEFORE IT GOES LIVE — FILL THESE IN
-----------------------------------

Everything highlighted YELLOW with a dotted underline on the page is a
placeholder. Open index.html in any text editor and search for "[" to find
them all. The list:

  - [X business days]          turnaround time
  - [X hours]                  how fast you send a mockup
  - [neighborhood]             where customers pick up (appears 3 times)
  - [largest size]             biggest shirt size you stock
  - [DTF / DTG / screen print] which methods you actually run
  - $00                        ALL the pricing numbers (the table + add-ons)
  - [$0]                       back/sleeve print and 2XL+ upcharges
  - [Owner name]               who runs the shop
  - [designing / printing]     what you've been doing
  - [X years]                  how long
  - [phone] [email]            contact info in the footer
  - [@instagram]               social handle
  - [street address]           pickup address
  - [neighborhood, MN ZIP]     city and zip
  - [hours]                    when you're open

Also in the <head> at the top of the file:
  - The LocalBusiness block has [PHONE], [EMAIL], [STREET ADDRESS],
    [CITY], [ZIP]. Google reads this for "custom t shirts near me"
    searches — worth filling in properly.
  - og:image points at share.jpg, which doesn't exist yet. Add a
    1200x630 photo of your printed shirts to the site root and name it
    share.jpg, or the link preview will be blank when people text it
    around.


THE PHOTO GALLERY
-----------------

The "Our work" section has six dashed boxes that say what photo goes in
each one. They are empty on purpose — for a print shop, photos of your
actual prints sell better than anything written on the page.

To add a real photo, find a block like this:

  <div class="shot"><b>Photo 1</b><span>A crew in their shirts, on the job</span></div>

and replace the whole thing with:

  <img class="shot" src="photo1.jpg" alt="A landscaping crew in custom MP Design Lab shirts">

then put photo1.jpg in the same folder as index.html.


THE QUOTE FORM
--------------

Right now the form shows a "not connected yet" notice instead of sending
anything. To make it work, open index.html, find:

  action="PASTE-YOUR-FORM-ENDPOINT-HERE"

and replace it with a real endpoint. Easiest free options:

  - Formspree (formspree.io) — sign up, create a form, paste the URL
  - Basin (usebasin.com) — same idea
  - Netlify Forms — if hosting on Netlify, instead add the attribute
    data-netlify="true" to the <form> tag

As soon as the placeholder text is gone from the action, the page stops
intercepting the submit and the form posts for real. No other changes
needed.

The file upload field only reaches you if the form service supports
attachments — Formspree and Basin both do on paid plans, free plans
usually don't. If you stay on a free plan, either remove the upload field
or add a line telling people to email their artwork instead.


ONE LEGAL NOTE
--------------

The footer says we can't reproduce licensed marks — college, NFL, NHL and
MLB logos. Leave that line in. In Minnesota people ask for Gophers, Vikings,
Twins and Wild constantly, and printing them without a license is trademark
infringement. The line turns the "no" into an offer to design something
original instead.
