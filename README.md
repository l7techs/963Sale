# 963Sale website

Public website for the **963 Sale** Syrian marketplace app (new and used items), in English and Arabic.

| Page | English | العربية |
| --- | --- | --- |
| Home | `/` | `/ar/` |
| Privacy Policy | `/privacy.html` | `/ar/privacy.html` |
| Terms of Service | `/terms.html` | `/ar/terms.html` |
| Contact Us | `/contact.html` | `/ar/contact.html` |
| Delete account request | `/delete-account.html` | `/ar/delete-account.html` |

Plain static HTML/CSS, served by GitHub Pages — no build step.

The Contact and Delete-account forms insert into the app's Supabase `contact_messages`
table using the public anon key (see `assets/forms.js`). That table is created by
`supabase/migrations/20261109000004_contact_messages.sql` in the app repo — run it once in
the Supabase SQL Editor, otherwise the forms show "Could not send". Row-level security only
allows inserting new messages; admins read them in Supabase → Table Editor → `contact_messages`.
Deletion requests arrive with topic `account` and start with `[ACCOUNT DELETION REQUEST — Website]`.

`assets/logo.svg` is icon concept D1 (awning + 963 + SALE); replace it when the final app icon is chosen.
