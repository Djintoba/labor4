---
author:
- |
  NONOGA Djintoba\
  Student ID: 1032249064
date: 2026-01-03
title: Exercises LaTeX - Behavior of floats and references
---

# Creating an image

This picture

::: center
![image](example-image){height="3cm"}
:::

is an imported PDF.

# Exploring image sizing keys

## Images with different sizes

<figure id="fig:with_text" data-latex-placement="ht">
<img src="example-image-b" style="width:50.0%" />
<figcaption>Image with width=0.5\textwidth</figcaption>
</figure>

<figure id="fig:height" data-latex-placement="ht">
<img src="example-image-c" style="height:50.0%" />
<figcaption>Image with height=0.5\textheight</figcaption>
</figure>

<figure id="fig:scale" data-latex-placement="ht">
<img src="example-image" />
<figcaption>Image with scale=0.3</figcaption>
</figure>

<figure id="fig:angle" data-latex-placement="ht">
<img src="example-image" />
<figcaption>Image with 50 degree rotation</figcaption>
</figure>

## Comparison \\textwidth and \\linewidth

<figure id="fig:textwidth" data-latex-placement="ht">
<img src="example-image-a" style="width:80.0%" />
<figcaption>Using of \textwidth (80%)</figcaption>
</figure>

<figure id="fig:linewidth" data-latex-placement="ht">
<img src="example-image-b" style="width:80.0%" />
<figcaption>Using of \linewidth (80%)</figcaption>
</figure>

# Testing of position specifiers

<figure id="fig:top" data-latex-placement="t">
<img src="example-image-a" style="width:70.0%" />
<figcaption>Figure positioned at the top (t)</figcaption>
</figure>

<figure id="fig:bottom" data-latex-placement="b">
<img src="example-image-c" style="width:70.0%" />
<figcaption>Figure positioned at the bottom</figcaption>
</figure>

<figure id="fig:here" data-latex-placement="ht">
<img src="example-image-c" style="width:70.0%" />
<figcaption>Figure positioned here (h)</figcaption>
</figure>

<figure id="fig:page" data-latex-placement="p">
<img src="example-image" style="width:80.0%" />
<figcaption>Figure on dedicated page (p)</figcaption>
</figure>

<figure id="fig:force" data-latex-placement="!ht">
<img src="example-image-a" style="width:60.0%" />
<figcaption>Figure with forced placement (!ht)</figcaption>
</figure>

# Sections and equations

## Sections and subsections

## First section {#sec:first}

This section has a label `sec:first`.

### Subsection example {#subsec:example}

This subsection has a label `subsec:example`.

## Numbered list

1.  First item[]{#item:first label="item:first"}

2.  Second item[]{#item:second label="item:second"}

3.  Third item[]{#item:third label="item:third"}

## Equations with labels

$$\begin{equation}
\label{eq:labelone}
e^{i\pi}+1=0
\end{equation}$$

$$\begin{equation}
\label{eq:labeltwo}
a^2 + b^2 = c^2
\end{equation}$$

# Labels testing with float

## Label before caption

<figure id="fig:before" data-latex-placement="ht">
<img src="example-image-b" style="width:60.0%" />
<figcaption>Figure with label defined before the legend</figcaption>
</figure>

## Label after caption

<figure id="fig:after" data-latex-placement="ht">
<img src="example-image-c" style="width:60.0%" />
<figcaption>Figure with label defined after the legend</figcaption>
</figure>

# Personal image

<figure id="fig:perso" data-latex-placement="ht">
<img src="mon_image.png" style="width:80.0%" />
<figcaption>Personal image</figcaption>
</figure>

# Cross references

## Figure references

Figure with \\textwidth: [5](#fig:textwidth){reference-type="ref" reference="fig:textwidth"}\
Figure with \\linewidth: [6](#fig:linewidth){reference-type="ref" reference="fig:linewidth"}\
Figure at top: [7](#fig:top){reference-type="ref" reference="fig:top"}\
Figure at bottom: [8](#fig:bottom){reference-type="ref" reference="fig:bottom"}

## Sections references

Section: [4.2](#sec:first){reference-type="ref" reference="sec:first"}\
Subsection: [4.2.1](#subsec:example){reference-type="ref" reference="subsec:example"}

## Equations references

Equation 1: [\[eq:labelone\]](#eq:labelone){reference-type="ref" reference="eq:labelone"}\
Equation 2: [\[eq:labeltwo\]](#eq:labeltwo){reference-type="ref" reference="eq:labeltwo"}

## Items references

Item 1: [\[item:first\]](#item:first){reference-type="ref" reference="item:first"}\
Item 2: [\[item:second\]](#item:second){reference-type="ref" reference="item:second"}\
Item 3: [\[item:third\]](#item:third){reference-type="ref" reference="item:third"}

# Conclusion

## Observed behavior

- `\textwidth` vs `\linewidth`: In two-column mode, `\linewidth` corresponds to the width of the current column, while `\textwidth` corresponds to the total width of the page.

- Position specifiers:

  - `h`: Here if possible

  - `t`: At the top of the page

  - `b`: At the bottom of the page

  - `p`: Dedicated page

  - `!`: Force placement

- Labels and references: 2 compilations are necessary for the references to be correct.

- Label before `\caption`: The reference points to the section rather than the figure.

- Label after `\end{equation}`: The reference is not working properly.
