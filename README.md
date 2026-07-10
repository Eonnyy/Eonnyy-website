# 🖥️ Eonn.yy — A Windows 95 Themed Personal Website

A nostalgic, desktop-inspired personal website built to look and feel like a classic Windows 95 desktop — complete with draggable-looking windows, a working music player, a live guestbook, and project cards pulled straight from GitHub.

**🌐 Live site:** [eonnyy.neocities.org](https://eonnyy.neocities.org/)

![Made with Claude](https://img.shields.io/badge/Built%20with-Claude%20AI-6B4FBB?style=flat-square)
![No Framework](https://img.shields.io/badge/Stack-HTML%2FCSS%2FJS-orange?style=flat-square)
![Deploy](https://img.shields.io/badge/Hosted%20on-Neocities-8A2BE2?style=flat-square)

---

## ✨ Features

- **🪟 Windows 95 desktop UI** — authentic title bars, beveled borders, and that unmistakable gray/navy color scheme
- **⚡ Single-page navigation** — switching between About Me, Projects, and Guestbook happens instantly with a smooth fade transition, no page reloads
- **🎵 Custom music player** — retro-styled widget with play/pause/skip controls and a live progress bar, streaming tracks from external links
- **📖 Live guestbook** — powered by [giscus](https://giscus.app), backed by GitHub Discussions, so visitors can leave real comments using their GitHub account
- **📌 Live project cards** — the Projects tab pulls repo info directly from GitHub using auto-generated pin cards, plus optional custom thumbnails per project
- **📱 Responsive layout** — collapses gracefully into a single column on smaller screens
- **🎨 Fully custom CSS** — no UI framework, hand-built Windows 95 component system (title bars, buttons, scrollable panels)

## ▶️ Running the Site

**See it live:** [eonnyy.neocities.org](https://eonnyy.neocities.org/)

To run it yourself locally (e.g. to preview changes before uploading):

1. Clone or download this repo
2. Open `index.html` directly in your browser — no build step, no server needed

> **Heads up:** the GitHub API-based features (Guestbook and Projects) may behave differently when opened locally via `file://`, since some browsers block cross-origin requests from local files. To test those two tabs properly, upload the files to your actual host (Neocities, Vercel, GitHub Pages, etc.) and view it from there.

## 🛠️ Built With

- HTML5, CSS3, and vanilla JavaScript — no frameworks, no build step
- [giscus](https://giscus.app) for the guestbook (GitHub Discussions-backed comments)
- [github-readme-stats](https://github.com/anuraghazra/github-readme-stats) for auto-generated repo cards
- Hosted on [Neocities](https://neocities.org)

## 🤖 How This Was Built

This site was built collaboratively with **[Claude AI](https://claude.ai)** by Anthropic — from the initial Windows 95 layout, to the music player logic, to wiring up the GitHub Discussions-based guestbook. It's a good example of iterating on a static site design conversationally instead of writing every line by hand.

## 📁 Project Structure

```
├── index.html              # Main site (About Me / Projects / Guestbook, single file)
└── src/
    └── assets/
        ├── eonnyy_banner.jpg
        ├── profile.jpg
        └── projects/
            └── toro-wallpaper-gallery.jpg   # Project thumbnails
```

## ⚙️ Configuration

All the editable bits live in one `CONFIG` object near the bottom of `index.html`:

```js
const CONFIG = {
    githubUsername: 'Eonnyy',
    projectRepos: [
        { repo: 'Toro_Wallpaper_Gallery', image: '/src/assets/projects/toro-wallpaper-gallery.jpg' },
        // add more repos here
    ],
    giscus: {
        repo: 'your-username/your-guestbook-repo',
        repoId: '...',
        category: 'Guestbook',
        categoryId: '...'
    }
};
```

- **Add a project** → add an entry to `projectRepos` (thumbnail is optional)
- **Add a song** → add an entry to the `tracks` array further down, with a direct link to the audio file
- **Set up your own guestbook** → follow the [giscus setup guide](https://giscus.app) and paste your own repo/category IDs in

## 🚀 Deployment Notes

This site is designed to run on **static hosting** (Neocities, Vercel, GitHub Pages, etc.) with zero build step — just upload the files as-is.

> **Note on Neocities free tier:** free accounts enforce a strict Content Security Policy that blocks `fetch()` requests to external APIs. That's why Projects use `<img>`-based GitHub pin cards instead of a live API call — images aren't restricted by this policy, so the cards still work without needing a paid plan.

## 📜 License

Personal project — feel free to fork the structure/approach for your own site, just swap out the content and assets for your own. 💛
