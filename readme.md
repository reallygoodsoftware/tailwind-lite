# Tailwind Lite

Tailwind Lite is a stripped back version of [Tailwind](https://tailwindcss.com/) - the popular utility-first CSS framework, that can be added to your site or app with a single line of code (as opposed to the usual setup steps that Tailwind requires).

The benefits of using Tailwind Lite are easy setup and a lower maintenance burden. The drawback is that Tailwind Lite does not enable all of the classes that regular Tailwind does.

## Add Tailwind Lite in one line
```
<link rel="stylesheet" href="https://cdn.tailwind-lite.com/2.0.1.css" />
```

## Background
Tailwind is awesome. It has popularized a way of styling web pages that it is conceptually simple and reduces both complexity and conflicts as codebases grow, making them easier to contribute to and more maintainable. Because of it's popularity, it's utility classes are now recognizable across the industry, and there is a growing corpus of copy-pasteable tailwind snippets which can picked up from one codebase and dropped in another without breaking anything. 

At the same time, using Tailwind currently requires a developer to understand and work with NPM, and the javascript package ecosystem. This has the effect of 1. Discouraging less experienced contributors from working with it (E.g. designers who know HTML), and 2. Reducing the span of time within which contributors can modify the codebase before running into dependency issues and breaking changes in the future.

Tailwind Lite is an attempt to solve some of those problems. We've compiled the vast majority of the most used Tailwind classes, and put them into one ready-to-use file, allowing you to use Tailwind without a build step, by just loading this file in the head of your page. 

### Setup

Use the JsDelivr CDN

```
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/reallygoodsoftware/tailwind-lite@759f1d7/dist/2.0.1.css" />
```

Use the Tailwind Lite CDN

```
<link rel="stylesheet" href="https://cdn.tailwind-lite.com/2.0.1.css" />
```

Add it to your codebase directly

- Download the file from [here](https://cdn.tailwind-lite.com/2.0.1.css).
- Import this stylesheet as normal.


## What's Included

- The current list of classes included by default can be found [here](https://github.com/html-first-labs/static-tailwind/blob/master/src/classes.txt). 

## How It Works
- There is a single .txt file (`/src/classes.txt`) which contains a list of all of the classes we may need to use.  
- We use the tailwindcss npx command to parse this file and output a fully compiled css file that contains only these classes. 

## Customizing the defaults (adding or removing classes)

If you're not happy with the choice of classes we've included, you can also use this repository to make your own version of Tailwind Lite.

- Pull this repo
- Install npm & npx, then tailwind.
- Make whatever changes you need to the `/src/classes.txt`
- Run `npx @tailwindcss/cli -i ./src/inputv.css -o ./dist/NUMBER.css` to compile the file.
- Your compiled file is now available in `/dist/`. Include it in your codebase or host it on a CDN as required.