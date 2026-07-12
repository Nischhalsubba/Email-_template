# Repository Instructions

## Scope

This repository contains HTML email templates and design experiments. Browser rendering is useful for quick inspection but is not proof of email-client compatibility.

## Email conventions

- Prefer table-based layout for broad client support.
- Keep critical CSS inline or use a verified inlining step.
- Use absolute production URLs for hosted images and links.
- Include image dimensions, alt text, and sensible fallbacks.
- Keep the primary CTA clear and large enough for touch.
- Include a plain-text version for real sends.
- Add unsubscribe, sender identity, physical address, and required legal content for campaigns.

## Compatibility

Test important templates in:

- Gmail web and mobile
- Outlook desktop and web
- Apple Mail and iOS Mail
- dark mode
- blocked-image mode
- narrow mobile widths

## Verification

1. Validate HTML and links.
2. Send a real test email rather than relying only on browser preview.
3. Check subject, preheader, sender, and reply-to behavior.
4. Verify accessibility reading order and link labels.
5. Confirm tracking and personalization tokens match the sending platform.
6. Inspect final inlined markup.

## Do not

- Do not use JavaScript in email templates.
- Do not depend on unsupported CSS without fallbacks.
- Do not use fake unsubscribe links in production.
- Do not present the repository thumbnail as an inbox screenshot.
- Do not send purchased or unconsented lists.