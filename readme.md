# Static Tailwind

## Use static tailwind in one line
```
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/html-first-labs/static-tailwind/dist/tailwind.css" />
```

## About
Tailwind is awesome. It has popularized a way of styling web pages that it is conceptually simple and reduces both complexity and conflicts as codebases grow, making them easier to contribute to and more maintainable. Because of it's popularity, it's utility classes are now recognizable across the industry, and there is a growing corpus of copy-pasteable tailwind snippets which can picked up from one codebase and dropped in another without breaking anything. 

At the same time, using Tailwind currently requires a developer to understand and work with NPM, and the javascript package ecosystem. This has the effect of 1. Discouraging less experienced contributors from working with it (E.g. designers who know HTML), and 2. Reducing the span of time within which contributors can modify the codebase before running into dependency issues and breaking changes in the future.

Static Tailwind is an attempt to solve some of those problems. We've compiled the vast majority of the most used Tailwind classes, and put them into one ready-to-use file, allowing you to use Tailwind without a build step, by just loading this file in the head of your page. 

You can either download this file, or serve it from the jsdelivr CDN. If you do the latter, which supports gzip compression, the file size received by most of your users will be ~70kb. 

If you're not happy with the choice of classes we've included, you can also use this repository to make your own version of static tailwind. We've included steps below on how to do this

## What's Included

- The current list of classes included by default can be found [here](https://github.com/html-first-labs/static-tailwind@759f1d7/blob/master/src/classes.txt). 

## How It Works
- There is a single .txt file (`/src/classes.txt`) which contains a list of all of the classes we may need to use.  
- We use the tailwindcss npx command to parse this file and output a fully compiled css file that contains only these classes. 

## How to Use
- To use our default file, either:
  - Download the raw file [here](https://raw.githubusercontent.com/html-first-labs/static-tailwind/master/dist/tailwind.css), and include it in your codebase as normal.
  - Include this line in the head of your page to load it from a CDN: 
  ```
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/html-first-labs/static-tailwind@759f1d7/dist/tailwind.css" />
  ```
- To customize the classes that are included, see the instructions below.

## Customizing the defaults (adding or removing classes)
- Pull this repo
- Install npm & npx, then tailwind.
- Make whatever changes you need to the `/src/classes.txt`
- Run `npx tailwindcss -i ./src/input.css -o ./dist/tailwind.css` to compile the file.
- Your compiled file is now available in `/dist/tailwind.css`. Upload it to S3 or wherever you'd like to host it, and reference it normally in the head of your page. 
