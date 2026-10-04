# MitSna CMS content

Content for [mitsna.org](https://mitsna.org), edited with [Sveltia CMS](https://github.com/sveltia/sveltia-cms) at **https://mitsna.org/cms/**.
This repository holds content only — the website code lives in the website repository.

## What's here

| Path | Used by | Edited in the CMS as |
|---|---|---|
| `data/executives.json` | Team page (`/Team`) | **Executive team** — departments, each with its people |
| `data/members.json` | Members page (`/Members`) | **Members** — name and photo |
| `media/team/` | Photos for both pages | Uploaded through the photo fields |

The website reads these files straight from this repository (`raw.githubusercontent.com/MitSna-IT/CMS/main/...`)
each time the page loads, so a published change shows on the site within about five minutes. No rebuild is needed.

## Editing

1. Open https://mitsna.org/cms/ and sign in with GitHub. You need write access to this repository.
   - Without a one-click login set up, choose **Sign in with Token** and paste a GitHub
     [fine-grained personal access token](https://github.com/settings/personal-access-tokens/new) limited to
     `MitSna-IT/CMS` with **Contents: Read and write**.
2. Pick **Executive team** or **Members** in the sidebar, edit, and click **Save**. Saving commits to `main`.
3. Drag items to change their order on the page. A department with no people is hidden on the site.

Photos are resized to 800 px and converted to WebP on upload. Square, face-centred photos look best.

## File format

`data/executives.json`

```json
{
  "departments": [
    {
      "name": "Technology",
      "description": "Driving technological innovation and digital transformation",
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
  ]
}
```

Only `name` and `position` are required; leave out anything you don't have.

`data/members.json`

```json
{ "members": [{ "name": "Full Name", "photo": "/media/team/member-full-name.jpg" }] }
```
