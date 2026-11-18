# HTML email: compatibility, accessibility and delivery review

This repository contains an email template with **index.html** and image assets under **images/**. Rendering inside a browser does not guarantee the same result in Gmail, Outlook or a mobile email client. A release must distinguish inspected clients from assumptions.

## Content contract

- The message has a clear subject and preheader when integrated into an actual email campaign.
- The primary call to action states what happens after activation.
- Essential information is text, not exclusively embedded in images.
- Relevant links use meaningful accessible names and resolve to the correct destination.
- Prices, dates, offers and sender identity are verified from the approved campaign brief.
- Marketing emails include legally required sender identity and opt-out mechanisms for the applicable audience; do not invent unsubscribe links.
- No user-specific addresses, tracking tokens, customer exports or credentials appear in screenshots or source examples.

## Rendering acceptance matrix

| Environment or setting | What to inspect |
| --- | --- |
| Desktop browser preview | DOM structure, text order and missing asset links |
| Webmail client | Layout stability, link styles and image blocking |
| Desktop Outlook | Tables, spacing, dark-mode behavior and fallback fonts |
| Mobile email client | Narrow width, tap target sizing, readable body copy |
| Images disabled | Brand/message/CTA remains meaningful using text and alternative descriptions |
| Dark mode | Text and buttons retain usable contrast |
| High zoom | Meaningful reading order without clipped calls to action |
| Screen reader | Headings, link purpose and essential text are conveyed without decoration |

Only mark a client as “verified” after a real send-to-test-inbox rendering or an approved client-testing service. Do not infer it from a screenshot of another client.

## Local preview

From repository root:

~~~bash
python -m http.server 8000
~~~

Open http://localhost:8000/ and inspect index.html. This is a basic HTML/image preview, not a deliverability or inbox-placement test.

## Campaign release evidence

A PR should name the campaign purpose, audience, approved source copy, changed markup/assets, responsive captures, actual email clients tested, links checked, and known limitations. For image replacements, document source rights and optimized dimensions.

## Recovery

If an email renders incorrectly or contains a wrong link, stop subsequent sends and correct the template; previously delivered emails cannot be reliably modified. Preserve the error details without including recipient personal data.
