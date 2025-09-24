# Nostra — Simple E-commerce Frontend

**Nostra** is a lightweight, static e-commerce frontend built with HTML, CSS and vanilla JavaScript. It includes a home page, a product collection page with client-side search, and a responsive navigation UI — suitable as a portfolio project or starting point for a bigger store.

---

## Demo
Open `index.html` in your browser (or serve the folder with a static server) to see the site.

---

## Features
- Home page with hero, new arrivals and sections.
- Collection page with client-side search (type to filter product boxes).
- Responsive navbar and side menu.
- Simple, easy-to-read code — great for beginners.

---

## Tech stack
- HTML5
- CSS (external `style.css`)
- JavaScript (vanilla)

---

## Files / Project structure
```
/ (project root)
├─ index.html
├─ collection.html
├─ collection.js
├─ script.js
├─ style.css
├─ assets/         # product images used in the pages
└─ README.md
```

> Ensure `style.css` and the `assets/` folder are present in the repo so images and styles load correctly.

---

## Run locally

### Option A — Open directly
1. Clone the repo or copy files into a folder.
2. Double-click `index.html` (or open it with your browser).

### Option B — Serve with a simple HTTP server (recommended)
If you have Python installed, from the project folder run:

```bash
# Python 3
python -m http.server 8000
```

Then open `http://localhost:8000` in your browser.

---

## Git / GitHub — quick commands

```bash
# if you haven't already
git init
git add .
git commit -m "Initial commit — Nostra ecommerce frontend"
# create a repo on GitHub, then:
git remote add origin https://github.com/<your-username>/<repo-name>.git
git branch -M main
git push -u origin main
```

If you are cloning an existing repo:

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
# add files, commit, push as above
```

---

## Small bug fix (collection.js)
I noticed `collection.js` uses `event` but the listener parameter isn't defined. Use the parameter `e` (or `event`) in the function to avoid errors. Replace your current `collection.js` with this corrected version:

```javascript
// collection.js (fixed)
var productContainer = document.getElementById("product");
var search = document.getElementById("search");
var productlist = productContainer.querySelectorAll("div");

search.addEventListener("keyup", function(e) {
    var enteredValue = e.target.value.toUpperCase();
    for (var count = 0; count < productlist.length; count++) {
        var productname = productlist[count].querySelector("p").textContent;
        if (productname.toUpperCase().indexOf(enteredValue) < 0) {
            productlist[count].style.display = "none";
        } else {
            productlist[count].style.display = "block";
        }
    }
});
```

(You can also improve by targeting `.product-box` specifically so other `div`s aren't matched.)

---

## To improve (suggestions)
- Add `contect.html` → rename to `contact.html` (spelling) and implement a working contact form.
- Add `README` screenshots (drag images into the repo and reference them in the README).
- Add `style.css` if missing, or split into `styles/` and keep components modular.
- Consider adding `package.json` and a build step if you add frameworks later.
- Add `LICENSE` (MIT recommended) and a `CONTRIBUTING.md` for collaborators.

---

## License
This project is released under the **MIT License** — include a `LICENSE` file if you want this.

---

## Contact
Maintainer: **Nanthapandi**  
(Replace with your email / GitHub profile link.)
