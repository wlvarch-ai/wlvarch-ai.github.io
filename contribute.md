---
title: Contribute
permalink: /contribute/
lead: How to add a session write-up, workflow, showcase entry, tool or reading. No GitHub experience needed.
---

Everything on this site is a plain text file in a GitHub repository. To add something, you create or edit a file and ask for it to be added. This request is called a **pull request**. A member of the editorial group reviews it, may suggest changes, and then merges it. The site updates itself a minute or two later.

All of this can be done in a web browser. You don't need to install anything.

## Before you start

1. Create a free account at [github.com](https://github.com). A handle that isn't your full name is fine.
2. Tell the editorial group your handle at the next session if you want to be added to the organisation. Members can work directly in the repository. Everyone else can still contribute through a fork (see below).
3. Read the [posting rules]({{ '/ethics/' | relative_url }}#our-posting-rules). Pull requests that break them won't be merged.

## What goes where

| You want to add | Folder | File name | Start from |
| --- | --- | --- | --- |
| A session write-up | `_posts` | `YYYY-MM-DD-short-title.md` | `_templates/session-post.md` |
| A workflow | `_workflows` | `short-title.md` | `_templates/workflow.md` |
| A showcase entry | `_showcase` | `short-title.md` | `_templates/showcase.md` |
| A tool review | `_data/tools.yml` | edit the existing file | the example in that file |
| A research or reading item | `reading.md` | edit the existing file | the format on that page |
| Images | `assets/images/YYYY/short-title/` | `descriptive-name.jpg` | under 500 KB each |

File names use lower case letters and hyphens only, with no spaces. A session post must start with the session date, or the site will not list it. A post dated in the future will not appear until that date.

## Adding a session write-up (step by step)

1. Open the repository on GitHub and go into the `_templates` folder.
2. Open `session-post.md`, click the **Raw** button, and copy all the text.
3. Go back to the repository's main page and open the `_posts` folder.
4. Click **Add file → Create new file**.
5. Name the file, for example `2026-11-04-prompting-for-precedent-research.md`.
6. Paste the template and fill in the fields between the `---` lines. Then write the post underneath.
7. Click **Preview** to check it reads properly.
8. Click **Commit changes…**. Choose **Create a new branch for this commit and start a pull request**, give it a short description, and confirm.
9. On the next screen, click **Create pull request**.

If you are not yet a member of the organisation, GitHub will offer to **fork** the repository at step 4 (make your own copy). Accept, and the rest of the steps are the same.

## Adding images

1. In the repository, go to `assets/images/`.
2. Click **Add file → Upload files**. Type the folder path into the file name box first (e.g. `2026/prompting-for-precedent-research/`) so the folder is created.
3. Upload on the same branch as your post.
4. In your post, reference the image like this:

{% raw %}
```markdown
![What the image shows, for screen readers]({{ '/assets/images/2026/prompting-for-precedent-research/plan-test.jpg' | relative_url }})
*Caption: what it shows and which tool produced it.*
```
{% endraw %}

Keep each image under 500 KB. Export at 1600 px wide or less. Images of people need their consent. Images of other students' work need their permission.

## Adding a tool

Open `_data/tools.yml`, click the pencil icon to edit, and add an entry in this format. Indentation matters: use two spaces, not tabs.

```yaml
- name: Tool name
  url: https://example.com
  used_for: What you actually used it for
  cost: Free tier / paid (approx. £ per month)
  data_terms: Does it train on uploads? Who owns outputs?
  verdict: One or two honest sentences
  reviewed: 2026-11-04
  reviewer: Your first name or handle
```

Only add tools you have used on real work. If you are updating an existing entry, change the `reviewed` date and the `reviewer`.

## What reviewers check

The editorial group checks every pull request against this list before merging:

- [ ] Front matter is complete, including `ai_disclosure`
- [ ] Facts and links are correct; sources are linked
- [ ] No full names or faces without consent
- [ ] Limitations and failures are stated, not just successes
- [ ] Images are under 500 KB with alt text and a caption
- [ ] Written in plain UK English, and in your own words

Reviewers will leave comments rather than reject outright. Reply, make the change on the same branch, and the pull request updates automatically.

## Previewing the whole site on your own computer (optional)

This is only needed for changes to layouts or styles. Install Ruby, then in the repository folder run:

```bash
bundle install
bundle exec jekyll serve
```

Open `http://localhost:4000` in a browser.

## Getting stuck

Bring it to the next session. Getting stuck on a pull request is a normal part of learning version control. It is exactly what practice teams deal with on shared models.
