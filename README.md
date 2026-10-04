# MitSna CMS content

Content for [mitsna.org](https://mitsna.org), edited with [Sveltia CMS](https://github.com/sveltia/sveltia-cms) at **https://mitsna.org/cms/**.
This repository holds content only — the website code lives in the website repository.

## What's here

| Path | Used by | Edited in the CMS as |
|---|---|---|
| `content/executives/<department>.json` | Team page (`/Team`) | **Executive team** — one entry per department, each with its executives |
| `data/members.json` | Members page (`/Members`) | **Members** — name and photo |
| `media/team/` | Photos for both pages | Uploaded through the photo fields |

The website reads these files straight from this repository (it lists `content/executives/` with the GitHub API and loads each file from `raw.githubusercontent.com`)
each time the page loads, so a published change shows on the site within about five minutes. No rebuild is needed.

## Editing

1. Open https://mitsna.org/cms/ and sign in with GitHub. You need write access to this repository.
   - Without a one-click login set up, choose **Sign in with Token** and paste a GitHub
     [fine-grained personal access token](https://github.com/settings/personal-access-tokens/new) limited to
     `MitSna-IT/CMS` with **Contents: Read and write**.
2. **Executive team:** each department is its own entry.
   - Open a department to add, edit, reorder (drag) or remove its executives, then **Save**.
   - **New Department** adds a department; delete one from inside it. Departments with no executives are hidden on the site.
   - **Display order** sets the department order on the Team page (lowest first: 10, 20, 30…).
3. **Members:** one list. Add, edit, remove or drag members to reorder, then **Save**.
4. Every save commits to `main`; the site picks it up within a few minutes.

Photos are resized to 800 px and converted to WebP on upload. Square, face-centred photos look best.

## File format

`content/executives/technology.json` (one file per department)

```json
{
  "name": "Technology",
  "description": "Driving technological innovation and digital transformation",
  "order": 30,
  "members": [
    {
      "name": "Full Name",
      "position": "IT Specialist",
      "photo": "/media/team/executive-full-name.jpg",
      "bio": "…",
      "current_role": "…",
      "achievements": ["…"],
      "specialties": ["…"],
      "email": "name@mitsna.org",
      "linkedin": "https://…",
      "twitter": "https://…",
      "instagram": "https://…",
      "website": "https://…"
    }
  ]
}
```

Only `name` and `position` are required; leave out anything you don't have.

`data/members.json`

```json
{ "members": [{ "name": "Full Name", "photo": "/media/team/member-full-name.jpg" }] }
```
