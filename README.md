# What-is-wrong-with-my-Tex-and-Sweave
I have problems using Rstudio Sweave while compiling with Knitr. I have MacTex installed on my Mac and Tex Live installed on my Win 11. When I tried to compile this Rnw file to PDF, I have different problems.

**Problems when using Tex Live + Sweave (Knitr) on Win 11 - Tex Capacity exceed**
I found "texmf.cnf" but I did not manage to edit it. This is not a read-only file but the folder is. I tried to change it but it automatically changed it back immediately.
There is no big plot in this Rnw.file.
Compiling with Sweave does not have problems. But I need Knitr. I just need highlight in the codes in that PDF.

**Problems when using Tex Live + Sweave (Knitr) on Mac -
Package fontenc Error: Encoding file 't2aenc.def' not found.
Package fontenc Error: Encoding file 'ly1enc.def' not found.
Latex Error: File 'xstring.sty' not found.**

**----------update----------** 

The problems on Mac became "incompatible color definition".


**----------update2----------** 

Removed "\usepackage{tikz}' and anything relevant with tikz from 'structure' and installed tikzdevice package in R. 

The R function "ci" for calculating confidence interval generates warning messages by default. Added "warning = FALSE" in the code chuncks with this function to avoid "dimension too large" error. 

**Mac** problem: ! Package tikz Error: Sorry, image externalization failed: the resulting image was EMPTY; Package xcolor Warning: Incompatabile color definition on (a lot of lines)

**Win 11** problem: ! Package tikz Error: Sorry, image externalization failed: the resulting image was EMPTY. 

**----------update3----------** 

Problem solve! Mac and Win both can compile a PDF now. 

What is remaining about tikz in my strucutre tex file to make it work:

\usepackage{tikz}

\usetikzlibrary{matrix}

\usetikzlibrary{babel}

\usepackage{pgfplots}

\usepgfplotslibrary{external}


I removed "\tikzexternalize{main}"