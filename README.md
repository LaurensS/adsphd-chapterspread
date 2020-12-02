ADS PhD LaTeX template -- Custom Chapter Opening
================================================

*This template is an example of a custom chapter opening in the adsphd template.
Given the impact of this change:
the complexity of this modification,
the incompatibility of titlesec with biblatex,
requiring the previous chapters to end on odd page to avoid a blank recto page;
I have currently opted to offer it as a template modification instead of merging in it in the main repository.*

**Since this is just a modification to illustrate the custom chapter opening, always refer to the [main repository](https://github.com/wannesm/adsphd) for the last version of the `adsphd` template.
This repository will not be updated to keep track of all those changes.**


What is this custom chapter opening?
------------------------------------
In my [thesis](https://lirias.kuleuven.be/retrieve/589409), I preferred to open a chapter on a complete page spread with a local table of contents on the left-side and the chapter itself on the right side.

The image below illustrates what this looks like in the template thesis text:
![Chapter opening example](/ExampleChapterOpening.png?raw=true "Example")

What do I need to know before using this?
-----------------------------------------

This repository includes a `preamble.tex` file with all the code needed to introduce this change.
This needs file needs to be loaded in the main `thesis.tex`: `\input{preamble.tex}`.

`Titlesec` is incompatible with `biblatex`, if you want to customize the local table of contents with `titlesec` as done in this example, you cannot use `biblatex`.

`Hyperref` must be loaded afterwards.
To use this modification, `adsphd` documentclass must be loaded with the `nohyperref` option.
The `preamble.tex` file loads `hyperref` at the end.


How can I use it?
-----------------

The custom opening is triggered with the following code:
```latex
\csname @openrightfalse\endcsname
\setboolean{spreadchapter}{true}
```

To prevent the final chapters, such as the bibliography from having this additional table of contents, toggle it off again.

```latex
\setboolean{spreadchapter}{false}
\csname @openrighttrue\endcsname
```

For any other information about the main `adsphd` documentclass refer to the [main repository](https://github.com/wannesm/adsphd).
