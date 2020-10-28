# Introduction to V Programming

V lang is a simple, fast, safe, compiled language for developing maintainable software. Despite being simple, V gives a lot of power to the developer and can be used in pretty much every field, including systems programming, webdev, gamedev, GUI, mobile (wip), science, embedded, tooling, etc.

## Why V-lang ?

**Performance**
      As fast as C (V's main backend compiles to human readable C)
      C interop without any costs
      Minimal amount of allocations
      Built-in serialization without runtime reflection
      Compiles to native binaries without any dependencies: a simple web server is only 65 KB
 
**Fast compilation**
      V compiles between ≈80k (Clang backend) and ≈1 million (x64 and tcc backends) lines of code per second per CPU core.
      (Intel i5-7500, SM0256L SSD, no optimization)
      V is written in V and compiles itself in under a second. 

**Small and easy to build compiler**
      V can be bootstrapped in under a second by compiling its code translated to C with a simple      

**C translation (wip)**
      V can translate your entire C project (wip) and offer you the safety, simplicity, and 10-25x compilation speed-up.

**Hot code reloading**
Get your changes instantly without recompiling.

Since you also don't have to get to the state you are working on after every compilation, this can save a lot of precious minutes of your development time.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/Allan-Alexander/V-Programming/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
