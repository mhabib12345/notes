---
title: "Add a Katex to Hugo Website"
date: 2024-03-27
math: true
---

If you're downloading manually:

1. Go to [KaTeX GitHub Releases](https://github.com/KaTeX/KaTeX/releases)

2. Download the latest katex.tar.gz or katex.zip

3. Extract all and copy to static folder (see below!)

{{< highlight plaintext >}}
static/
└── katex/
    └── katex.min.css
    ├── katex.min.js
    └── contrib/              ← Essential folder name
        └── auto-render.min.js
{{< /highlight >}}


4. Once your files are in the right place, your layouts/partials/katex.html should reference them with the correct paths:

{{< code language="css" >}}
<!-- KaTeX CSS -->
<link rel="stylesheet" href="/katex/katex.min.css">

<!-- KaTeX core JS -->
<script defer src="/katex/katex.min.js"></script>

<!-- Auto-render extension - NOTE the contrib/ path! -->
<script defer src="/katex/contrib/auto-render.min.js"
    onload="renderMathInElement(document.body, {
        delimiters: [
            {left: '$$', right: '$$', display: true},
            {left: '$', right: '$', display: false}
        ]
    });">
</script>
{{</code >}}

5. Add this to your layouts/_default/baseof.html or layouts/partials/head.html:

{{< code language="html" >}}
{{ if .Params.math }}
  {{ partial "katex.html" . }}
{{ end }}
{{</code >}}

6. Try to test!


Inline Math
Use single dollar signs ```$...$``` for math within text:

example : x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}

it will be shown as :

The quadratic formula $x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$ solves any quadratic.

Display Math
Use double dollar signs ```$$...$$``` for centered equations:
example : x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}

it will be shown as :
$$
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
$$
