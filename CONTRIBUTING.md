# Contributing to TSE Learning Hub

Every change — including adding yourself to the Team page — goes through
the same workflow. Working through it is part of the point.

## Workflow

```
Fork / Clone
     ↓
Create a branch
     ↓
Make your change
     ↓
Commit
     ↓
Push
     ↓
Open a pull request
     ↓
Get reviewed
     ↓
Merge
     ↓
Deploy (automatic)
```

## 1. Fork and clone

```bash
git clone https://github.com/<your-username>/tse-learning-hub.git
cd tse-learning-hub
```

## 2. Create a branch

Don't work directly on `main`. Name your branch after what it does:

```bash
feature/add-<your-name>-profile
feature/update-<your-name>-progress
feature/add-<your-name>-project
```

```bash
git checkout -b feature/add-your-name-profile
```

## 3. Adding your own profile page

Your profile is a real page you build — not a data file. This is meant
to be actual HTML/CSS practice, so take the freedom.

1. Copy the template folder, using your name (lowercase, hyphenated) as
   the folder name:
   ```bash
   cp -r team/members/_template team/members/your-name
   ```
2. Open `team/members/your-name/index.html` and fill in the four
   `<meta name="tse:*">` tags in the `<head>` — that's what the Team
   directory reads to build your card:
   ```html
   <meta name="tse:name" content="Your Full Name" />
   <meta name="tse:role" content="Trainee Software Engineer" />
   <meta name="tse:tagline" content="One line about what you're building." />
   <meta name="tse:github" content="https://github.com/your-username" />
   ```
3. Everything else on the page — and all of `style.css` — is yours to
   change. Rewrite the sections, change the layout, pick your own
   colors and fonts. The only requirement is that the four meta tags
   stay accurate.
4. Add your folder name to `team/members/index.json`:
   ```json
   ["your-name"]
   ```
5. Do not edit anyone else's folder, or `team.html`, or `js/team.js` —
   the directory picks up every listed member automatically.

## 4. Commit

Write commit messages that describe the change, not the file:

```bash
git add team/members/your-name team/members/index.json
git commit -m "Add your-name profile page"
```

## 5. Push

```bash
git push origin feature/add-your-name-profile
```

## 6. Open a pull request

Include:

- **Title** — e.g. "Add Jaswanth Kumar profile"
- **Description** — what you added
- **Testing** — how you checked it (e.g. "Verified locally with `python3 -m http.server`")
- **Checklist**:
  - [ ] Profile information added
  - [ ] Responsive design checked
  - [ ] No existing profile modified
  - [ ] Changes tested locally

## 7. Review

A teammate reviews your PR and may request changes. Push additional
commits to the same branch — they'll show up on the PR automatically.

## 8. Merge

Once approved, the PR is merged into `main`. No manual deployment step
is needed — the merge is what makes your profile show up on the live
site.
