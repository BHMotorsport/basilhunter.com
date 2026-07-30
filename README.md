# grahamstone.ai

Jekyll site for the GrahamStone Ventures motorsport program.
Hosted on GitHub Pages, same workflow as the RX2 site.

## Launch checklist

### 1. Create the repo and push

1. Create a new GitHub repo (public, or private on a paid plan)
2. Push this folder's contents to the `main` branch
3. In the repo: Settings > Pages > Source: Deploy from a branch > `main` / root

### 2. Point the domain

At your domain registrar, add these DNS records for grahamstone.ai:

| Type  | Host | Value               |
|-------|------|---------------------|
| A     | @    | 185.199.108.153     |
| A     | @    | 185.199.109.153     |
| A     | @    | 185.199.110.153     |
| A     | @    | 185.199.111.153     |
| CNAME | www  | YOUR-USERNAME.github.io |

Then in the repo: Settings > Pages > Custom domain > enter `grahamstone.ai`
and check "Enforce HTTPS" once the certificate appears (up to 24 hours,
usually much faster). The CNAME file in this repo keeps the setting sticky.

### 3. Contact form (done — Notion)

The contact page embeds a Notion form. Submissions land as rows in the
private Notion database "GrahamStone Motorsport — Website Inquiries" with Name,
Email, Company, Phone, Topic, and Message (all but Name required).
To change questions or the share link, open that database in Notion and
edit the "Contact Form" view. The embed URL lives in `contact.html`.

### 4. Replace placeholders before launch

- `assets/img/og-default.jpg` — default social share image, 1200x630px
- `assets/img/gallery/` — gallery photos, compressed under ~400KB, 1600px wide max
- `assets/img/partners/` — swap the placeholder SVGs for real partner logos (white/light versions read best on the navy band); update the links in `index.html` to each partner's site
- `gallery.md` — swap `VIDEO_ID` for real YouTube video IDs
- `events.html` — real event schedule
- `sponsors.md` — real partnership tiers and terms
- `_config.yml` — author email if a grahamstone.ai address gets set up
- `_posts/2026-07-25-sample-recap-template.md` — DELETE before launch (it is a template and will show on the live site)

## Posting an event recap

1. Copy the sample template in `_posts/`
2. Rename: `YYYY-MM-DD-short-title.md` (date prefix required)
3. Fill in the front matter (title, date, venue, image, description)
4. Write the recap, push to GitHub

It publishes automatically and appears on the home page, events page, and
RSS feed (`/feed.xml`). The `image` field in the front matter becomes the
social share preview on LinkedIn, Facebook, and X.

## Local preview (optional)

```
bundle install
bundle exec jekyll serve
```

Then open http://localhost:4000

## Structure

```
_config.yml      site settings, plugins, permalinks
_layouts/        default, page, post templates
_includes/       nav and footer
_posts/          event recaps (one markdown file each)
assets/css/      stylesheet
assets/img/      photos (keep them web-compressed)
index.html       home
car.md           the car
events.html      schedule + recap feed
gallery.md       photos and video
sponsors.md      partnership pitch
contact.html     Formspree contact form
CNAME            custom domain binding
```
