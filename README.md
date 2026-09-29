# ☕ Access DB Generator

**The fuel for your data grind.**

A tiny tool that builds a ready-to-use Microsoft Access database, already filled with sample data, in a few clicks. No installs. No server. Just open the page and brew.

I made this because setting up dummy Access databases by hand is slow, boring, and honestly a waste of good coffee. So I turned it into a system.

👉 **Live tool:** `https://jrmdg31.github.io/SampleDbGenerator---For-ms-access---by-jerome/`
---

## 🎬 See it in action

  OPTION 2 (YouTube): replace VIDEO_ID with your video's ID, and use a screenshot as the thumbnail:
  [![Watch the demo](https://img.youtube.com/vi/OczU0eB0NvQ/maxresdefault.jpg)](https://www.youtube.com/watch?v=OczU0eB0NvQ)
  -->
*Short on time? The video shows the whole flow in under a minute: pick fields, generate, double-click, done.*

---

## What it does

You design your table. The tool generates the data and hands you a file that builds the Access database for you.

- **Build your own table:** start with First Name and Last Name, then add whatever you need
- **50+ ready-made presets:** personal, employment, contact, location, financial, and system/audit fields. Tap to add or remove
- **Custom fields:** add your own and pick any Access data type (Short Text, Long Text, Number, Date/Time, Currency, AutoNumber, Yes/No, OLE Object, Hyperlink, Lookup Wizard)
- **Drag to reorder:** grab the dotted handle and slide fields into place (arrow keys work too)
- **Name the columns your way:** `FirstName`, `first_name`, `First Name`, or anything you type
- **Control the data:** row count (up to 50,000), % of empty cells, and your own lists of genders, job titles, and locations
- **Pick the format:** `.mdb` for old Access (2000-2003), `.accdb` for 2007 and newer
- **Live preview:** see the first rows, the row and column count, an estimated size, and the `CREATE TABLE` SQL as you tweak
- **CSV option:** don't want the script? Download a CSV and import it into Access yourself
- **Runs 100% in your browser.** Nothing gets uploaded anywhere

## How to use it

1. Open the tool.
2. Set your file name, table name, and format.
3. Build your fields: tap presets, add custom ones, choose a data type for each, and drag them into the order you want.
4. Click **Generate & download Access builder**. You'll get a `.vbs` file.
5. Put that file in a folder and **double-click it**.
6. Your `.mdb` / `.accdb` shows up in the same folder, table and rows included. Done.

**Shortcut:** `Ctrl + Enter` generates the builder.

### Good to know about data types

- **AutoNumber:** Access allows only one per table. The tool will warn you if you add a second.
- **OLE Object:** the column is created, but left empty (there's no sample file to put in it).
- **Hyperlink and Lookup Wizard:** these use extra Access properties, set on a best-effort basis. If one doesn't apply on your machine, the column still works as plain text.

### Why a `.vbs` file and not the database directly?

Straight talk: browsers can't write real Access files. The format is proprietary and there's no reliable JavaScript library for it. So the page generates a small script with your data inside, and Windows uses its own Access/Jet engine to build the database on your machine. Same result, one extra double-click.

---

## Windows blocked the file? 🚧

If you see *"These files can't be opened. Your Internet security settings prevented one or more files from being opened,"* nothing is broken. Windows is just being careful with downloaded files.

**Easiest fix:**
1. Go to your `Downloads` folder.
2. Right-click the `.vbs` file → **Properties**.
3. Tick **Unblock** at the bottom → **Apply** → **OK**.
4. Double-click it again.

**PowerShell fix** (change the file name to yours):

```powershell
Unblock-File "$env:USERPROFILE\Downloads\SampleDB_builder.vbs"
```

**Still stuck?** Use **Download CSV only**, then in Access go to *External Data → New Data Source → From File → Text File*.

The tool also has this whole guide built in. Hit **"Blocked? Fix it"** at the top of the page.

---

## Built with old school PCs in mind

- Plain HTML, CSS, and JavaScript. No frameworks, no libraries, no build step
- `.mdb` mode uses the Jet engine that already ships with older Windows
- Works on Windows XP and newer (as long as Access or the database engine is around)
- Animations switch off automatically if your system has "reduce motion" on

| Your Access version | Use this format |
|---|---|
| Access 2000 / 2002 / 2003 | `.mdb` |
| Access 2007 and newer | `.accdb` (or `.mdb`, which still opens) |
| Access 97 and older | Not supported, sorry |

If you get *"Could not create the database,"* switch to `.mdb` and try again. If it still fails, that PC probably needs the free [Microsoft Access Database Engine](https://www.microsoft.com/en-us/download/details.aspx?id=54920).

Big tables (tens of thousands of rows) can take a while on older computers. Start small, then scale up.

---

## Run it locally

No setup at all:

```bash
git clone https://github.com/YOUR-USERNAME/access-db-generator.git
cd access-db-generator
```

Then open `index.html` in any browser. That's it. It works offline.

## Host your own copy on GitHub Pages

1. Push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Pick `main` and `/ (root)`, then save.
5. Wait a minute or two. Your site goes live at `https://YOUR-USERNAME.github.io/access-db-generator/`.

---

## 🤝 Want to contribute? Please do.

This is a small project, but it gets better with more hands (and more coffee). I'd love your help with anything, big or small:

- 🐛 **Found a bug?** Open an issue.
- 💡 **Got an idea?** New presets, new data types, better fake data, more languages. Tell me.
- 🧪 **Tested it on an old machine?** Tell me what worked and what didn't. That's gold.
- ✍️ **Spot a typo or want clearer instructions?** Send a pull request.
- 🎨 **Want to improve the design?** Go for it.

**How to contribute:**
1. Fork the repo.
2. Make a branch: `git checkout -b my-cool-change`
3. Make your changes (it's one `index.html`, so it's easy to dig into).
4. Open the page in a browser and try it out.
5. Open a pull request and tell me what you changed and why.

More details are in [CONTRIBUTING.md](CONTRIBUTING.md). First-timers are welcome. Everyone starts somewhere.

## 🆘 Ran into an error? Talk to me.

Don't just close the tab and give up. If something broke, I want to know so I can fix it for everyone.

The fastest way: **[open an issue](../../issues/new/choose)** and tell me:

- What you clicked and what happened
- The exact error message (a screenshot is perfect)
- Your Windows version and Access version
- Which format you picked (`.mdb` or `.accdb`)

Prefer a direct message? Reach me here:

- 📧 **Email:** [jerome.david.cs@gmail.com](mailto:jerome.david.cs@gmail.com)
- 💼 **LinkedIn:** [Jerome David](https://www.linkedin.com/in/jerome-david-810079271/)
- 🌐 **Portfolio:** [jerome-portfolio-seven.vercel.app](https://jerome-portfolio-seven.vercel.app/)

I usually reply within 24 to 48 hours.

---

## License

MIT. Use it, change it, share it. See [LICENSE](LICENSE).

## About me

I'm **Jerome David**, an independent operator who helps businesses turn repetitive work into systems that run themselves. This tool came from that same idea: less busywork, more building.

If you liked it, drop a ⭐ on the repo. It really makes my day.

*Efficiency brewed daily.* ☕
