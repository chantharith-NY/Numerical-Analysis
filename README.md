mkdir latex-tooltip-website
cd latex-tooltip-website

echo "# LaTeX Tooltip Website" > README.md

echo """## LaTeX Tooltip Website

This repository contains a simple website that displays mathematical formulas using LaTeX tooltips.

### Features
- Hover over theorem names to reveal their mathematical expressions.
- Uses MathJax for LaTeX rendering.
- Simple and lightweight HTML, CSS, and JavaScript implementation.

### How to Use
1. Clone this repository:
   ```sh
   git clone https://github.com/YOUR_GITHUB_USERNAME/latex-tooltip-website.git
   ```
2. Open `index.html` in a web browser.

### Hosting on GitHub Pages
To host this website on GitHub Pages:
1. Push the repository to GitHub.
2. Go to the repository settings.
3. Under "GitHub Pages", set the source to `main` and folder to `/ (root)`.
4. Your website will be available at `https://YOUR_GITHUB_USERNAME.github.io/latex-tooltip-website/`.

---

## File Structure
- `index.html` - Main webpage with LaTeX tooltips.
- `README.md` - Documentation.
- `.eslintrc.json` - Linting configuration.
- `package.json` - Project metadata.

""" > README.md

echo """<!DOCTYPE html>
<html lang=\"en\">
<head>
    <meta charset=\"UTF-8\">
    <meta name=\"viewport\" content=\"width=device-width, initial-scale=1.0\">
    <title>LaTeX Tooltip Website</title>
    <style>
        .tooltip {
            position: relative;
            display: inline-block;
            cursor: pointer;
            color: blue;
            text-decoration: underline;
        }
        .tooltip .tooltiptext {
            visibility: hidden;
            width: max-content;
            background-color: #f9f9f9;
            color: black;
            text-align: left;
            padding: 5px;
            border-radius: 5px;
            border: 1px solid #ddd;
            position: absolute;
            z-index: 1;
            bottom: 125%;
            left: 50%;
            transform: translateX(-50%);
            opacity: 0;
            transition: opacity 0.3s;
        }
        .tooltip:hover .tooltiptext {
            visibility: visible;
            opacity: 1;
        }
    </style>
    <script type=\"text/javascript\" async
      src=\"https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.7/MathJax.js?config=TeX-MML-AM_CHTML\">
    </script>
</head>
<body>
    <h1>LaTeX Tooltip Example</h1>
    <div class=\"tooltip\">Pythagorean Theorem
        <span class=\"tooltiptext\">$a^2 + b^2 = c^2$</span>
    </div>
</body>
</html>""" > index.html

echo """{
    \"name\": \"latex-tooltip-website\",
    \"version\": \"1.0.0\",
    \"description\": \"A website that displays LaTeX tooltips\",
    \"main\": \"index.html\"
}""" > package.json

echo """{
    \"extends\": \"eslint:recommended\",
    \"env\": {
        \"browser\": true,
        \"es2021\": true
    },
    \"rules\": {}
}""" > .eslintrc.json

git init
git add .
git commit -m "Initial commit"

echo "Repository setup complete."
