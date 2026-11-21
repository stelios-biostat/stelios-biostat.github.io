# Academic Website Template

A simple academic website you can copy, edit, and publish for free, all from your web browser. Built with [Quarto](https://quarto.org) and GitHub Pages.

Template created and maintained by [Javi Rudolph, PhD](https://javirudolph.github.io), Assistant University Librarian for Computational Literacy, UF George A. Smathers Libraries, Academic Research Consulting and Services (ARCS) Department.

---

## 1. Create your repository

1. Make a free [GitHub account](https://github.com/signup) if you don't have one. Choose a username you'd be happy to put on your CV: it becomes your web address.
2. At the top of this page, click the green **Use this template** button, then **Create a new repository**. (Don't fork it.)
3. **Repository name:** `YOUR-USERNAME.github.io`, using your exact GitHub username.
4. Keep it **Public** and click **Create repository**.

> **Why this name?** Every GitHub account gets one personal website at `username.github.io`. Projects you publish later appear under it, like `username.github.io/my-project`, so your name comes first.

## 2. Turn on publishing

1. In your new repository, go to **Settings > Pages**.
2. Under **Build and deployment > Source**, choose **GitHub Actions**.

From now on, every change you commit rebuilds and publishes your site automatically.

> **Skipped this step?** No problem. Your site still builds, but it won't go online until you turn this on. The **Actions** tab will remind you with a yellow note.

## 3. Customize your website (required)

You can do all of this on GitHub: click a file, click the pencil icon ✏️ to edit, then **Commit changes**. Every file has instructions inside it, in comments that never show on your site.

1. **`_quarto.yml`**: your site's settings. Replace every line marked `FIXME` (your name, username, email). Keep the indentation exactly as it is.
2. **`index.qmd`**: your home page. Write a short bio, add your photo, then delete the yellow FIXME box.
3. **`research.qmd`**: a short introduction to your research, a picture, and links to your work.
4. **`cv.qmd`**: save your CV as a PDF named exactly `cv.pdf` and upload it to the main page of your repository. It replaces the placeholder.

**Adding pictures:** open the `images` folder, click **Add file > Upload files**, then type the file name exactly (including capital letters and `.jpg` or `.png`) where the page asks for it.

## 4. Check your site

1. Click the **Actions** tab. A yellow dot means your site is building (1 to 2 minutes). A green check ✅ means it's done.
2. Visit `https://YOUR-USERNAME.github.io`.

**Green check, but no website?** Click the latest run in the **Actions** tab and look for a yellow note. It means publishing isn't turned on yet: do step 2, then go to **Actions > Publish website > Run workflow**.

**Red ❌?** Click it to see which step failed. Most often:
- A spacing or typo problem in `_quarto.yml`. Compare it with the original in this template.
- A picture or file name that doesn't match exactly. `Me.JPG` and `me.jpg` are different names.

---

## Optional but recommended

- **Add your site link to your repo.** On your repository's main page, click the ⚙️ next to **About** and tick **Use your GitHub Pages website**.
- **Change the look.** Try a different `theme:` in `_quarto.yml`, a different `template:` in `index.qmd`, or follow the steps in `custom.scss` to change colors and fonts.
- **Add pages.** Copy `research.qmd`, rename it (e.g. `teaching.qmd`), and add it to the menu in `_quarto.yml`.
- **Rewrite this README** so it describes your site, not the template.

---

## Working on your own computer

Editing on GitHub works well for small changes. Working on your own computer lets you **preview your site before it goes live** and is how most people build bigger projects. It takes some setup the first time, but you only do it once.

### What you need (one time)

1. **RStudio** ([download](https://posit.co/download/rstudio-desktop/)). Quarto comes included. You also need [R](https://cran.r-project.org/).
   Prefer a newer editor? [Positron](https://positron.posit.co/) works too.
2. **Git**, the tool that tracks your changes ([install guide](https://happygitwithr.com/install-git)).
3. **Connect Git to your GitHub account**, so RStudio can send your changes to GitHub.

   **Read first:** [Happy Git with R](https://happygitwithr.com/), chapters 7 to 9, explains what this step does and why. The [Managing Git(Hub) Credentials](https://usethis.r-lib.org/articles/git-credentials.html) guide covers the same steps more briefly.

   **In short,** these are the lines you'll run. In RStudio, copy each one into the **Console** (bottom left) and press Enter:

   ```r
   install.packages("usethis") # Only if it isn't installed yet

   # Tell Git who you are (use the email from your GitHub account)
   usethis::use_git_config(user.name = "Your Name", user.email = "you@ufl.edu")

   # Opens GitHub so you can create a token (a password for RStudio).
   # Click "Generate token" at the bottom, then copy the token.
   usethis::create_github_token()

   # Paste your token when asked
   gitcreds::gitcreds_set()
   ```

### Get your website onto your computer

1. On your repository's main page on GitHub, click the green **Code** button and copy the web address.
2. In RStudio: **File > New Project > Version Control > Git**.
3. Paste the address, choose where to save the folder on your computer, and click **Create Project**.

### Preview your changes

1. Open any `.qmd` file and make a change.
2. Click **Render** at the top of the file. Your site opens in a preview window.
3. Keep editing and saving. The preview updates as you go. **Nothing is published yet:** only you can see it.

### Publish your changes

RStudio has a **Git** tab (top right) for this:

1. In the **Git** tab, tick the box next to each file you changed.
2. Click **Commit**, write a short message about what you changed (e.g. "Add new photo"), and click **Commit** again.
3. Click **Push** (the green up arrow). This sends your changes to GitHub.
4. GitHub rebuilds your site, just like when you edit online. Check the **Actions** tab for the green check.

**Editing on both GitHub and your computer?** Click **Pull** (the blue down arrow) in the Git tab before you start working, so your computer has the latest version.

---

## How this website is made

| Piece | What it does | Learn more |
|---|---|---|
| **Markdown** | The simple text formatting in `.qmd` files (`**bold**`, `## Heading`) | [Markdown basics](https://quarto.org/docs/authoring/markdown-basics.html) |
| **Quarto** | Turns your text files into a website | [Get started](https://quarto.org/docs/get-started/), [Creating a website](https://quarto.org/docs/websites/) |
| **YAML** | The settings at the top of each file and in `_quarto.yml` | [Website options](https://quarto.org/docs/reference/projects/websites.html) |
| **SCSS** | Your colors and fonts, in `custom.scss` | [HTML themes](https://quarto.org/docs/output-formats/html-themes.html) |
| **Git** | Keeps a history of every change | [Software Carpentry: Version Control with Git](https://swcarpentry.github.io/git-novice/) |
| **GitHub** | Stores your files online | [GitHub: Hello World](https://docs.github.com/en/get-started/start-your-journey/hello-world) |
| **GitHub Actions + Pages** | Build and publish your site every time you commit | [Quarto: Publishing to GitHub Pages](https://quarto.org/docs/publishing/github-pages.html) |

### Writing in Markdown

`.qmd` files are plain text. A few marks do most of the work:

| You type | You get |
|---|---|
| `**bold**` | **bold** |
| `*italic*` | *italic* |
| `## Heading` | a section heading |
| `[text](https://link.com)` | a link |
| `- item` | a bullet point |
| `![caption](images/photo.jpg)` | a picture |

---

## Learn more

**Quarto documentation**
- [Creating a website](https://quarto.org/docs/websites/)
- [About pages](https://quarto.org/docs/websites/website-about.html): all 5 home page layouts, with previews
- [HTML themes](https://quarto.org/docs/output-formats/html-themes.html): themes, colors, and `custom.scss`
- [Figures](https://quarto.org/docs/authoring/figures.html): sizing, captions, and layouts for pictures

**Git and GitHub**
- [Happy Git and GitHub for the useR](https://happygitwithr.com/) (Jenny Bryan): setup and everyday use with RStudio
- [Software Carpentry: Version Control with Git](https://swcarpentry.github.io/git-novice/)
- [GitHub Docs: Get started](https://docs.github.com/en/get-started)

**Example academic sites (with source code)**
- [Sam Shanny-Csik](https://samanthacsik.github.io) ([source](https://github.com/samanthacsik/samanthacsik.github.io))
- [Andrew Heiss](https://www.andrewheiss.com) ([source](https://github.com/andrewheiss/ath-quarto))

## Getting help

Open an issue in this repository, or book a consultation with UF Libraries ARCS: https://answers.uflib.ufl.edu/askarcs
