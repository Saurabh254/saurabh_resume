# Install required packages

```bash
sudo pacman -S texlive-basic texlive-latex texlive-latexextra texlive-binextra texlive-fontsrecommended texlive-xetex texlive-fontsextra
```

---

# Install VS Code extensions

Open **VS Code → Extensions** and install:

- Visual Studio Code
- LaTeX Workshop

The **LaTeX Workshop** extension provides:

- live preview
- auto compile
- forward/inverse search
- latexmk integration

---

# Configure LaTeX Workshop for XeLaTeX

Open **VS Code settings.json**

Press:

```
Ctrl + Shift + P
Preferences: Open Settings (JSON)
```

Add this:

```json
{
  "latex-workshop.latex.tools": [
    {
      "name": "xelatex",
      "command": "latexmk",
      "args": [
        "-xelatex",
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOC%"
      ]
    }
  ],

  "latex-workshop.latex.recipes": [
    {
      "name": "XeLaTeX",
      "tools": ["xelatex"]
    }
  ],

  "latex-workshop.latex.autoBuild.run": "onSave",
  "latex-workshop.view.pdf.viewer": "tab"
}
```
