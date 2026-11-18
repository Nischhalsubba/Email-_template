# Email client rendering and send-readiness matrix

## Purpose and implementation constraints
The root `index.html` is an XHTML Transitional email template with inline and embedded styles, an imported Google font, and Microsoft Outlook-specific conditional markup. Browser preview is **not** proof of Gmail/Outlook compatibility. This checklist applies to edits of HTML, styles, images, links, copy, tracking or personalization.

## Rendering matrix
| Client/environment | Minimum test | What to inspect |
| --- | --- | --- |
| Gmail web (desktop) | Normal and images blocked | Layout, clipped text, CTA and background fallback |
| Gmail Android | Narrow viewport, font scaling | Single-column stacking, tap targets, wrapped text |
| Outlook classic Windows | Word rendering engine | Table widths, spacing, buttons and MSO conditional comments |
| Outlook web/new Outlook | Desktop | Spacing, links, fonts, dark backgrounds |
| Apple Mail iOS | Light and dark appearance | Color inversion, image scaling, accessible labels |
| Apple Mail macOS | Desktop | Font fallback and layout stability |

Record the exact tested client version and date; do not mark unexecuted rows as passed. Real inbox tests or a dedicated rendering service are required to claim compatibility.

## Content and deliverability preflight
1. Confirm subject and preheader reflect the body and do not promise unavailable offers.
2. Replace campaign placeholders and merge tags **before sending**. Preview missing-name and empty-data fallbacks.
3. Validate absolute `https://` destinations, UTM parameters if used, and unsubscribe/preferences links required for the sending context.
4. Confirm sender identity, consent basis, required organization details and applicable disclosure requirements with the sending team.
5. Provide a readable plain-text alternative in the sending platform. The HTML file alone does not supply a multipart email.
6. Review external images, fonts and trackers for recipient privacy and approved hosting.

## Accessibility and degraded mode
- Preserve reading order when CSS is ignored; use descriptive headings and link text.
- Provide alt text conveying informative images; empty alt text for purely decorative ones.
- Confirm CTA text is actionable without relying on color alone.
- Test 200% text sizing and narrow screens without clipped content.
- Check text contrast in normal and dark appearances; never rely on background images for required text.
- Ensure images-off preview still conveys purpose, offer, and primary action.

## Release record
```text
Template commit:
Campaign / audience:
Sender / approver:
Test send timestamp:
Client and version / result / screenshot link:
Links checked (including unsubscribe):
Images blocked / dark mode / zoom outcome:
Merge-tag fallback test:
Plain-text alternative confirmed:
Exceptions, severity, owner and follow-up:
```

## Blocking conditions
Do not approve a send with broken primary CTA, missing opt-out where required, incorrect personalization, unreadable content with images blocked, or unapproved tracking. Resolve or explicitly scope any rendering exceptions. Roll back by restoring the previously approved HTML and sender-platform configuration; publishing this checklist does **not** alter any active campaign.
