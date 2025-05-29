# fsharp.org

This repository hosts the [fsharp.org](https://fsharp.org/) website. Pull requests are welcome.

The site is built using the popular static site generator [Jekyll](http://jekyllrb.com/docs/usage/),
which converts Markdown templates to HTML pages.

## Editing content

Most edits can be made by simply editing the appropriate Markdown file. Normally you'd simply:

- Fork the repository
- Make some changes locally
- Test them locally (e.g. by running `jekyll serve`)
- Open a pull request

If you prefer to make your edit directly within GitHub, there is a GitHub
Action which should build your fork automatically so you can confirm your
changes look okay.

## Testimonials

New testimonials are very welcome!

Simply add a new markdown file to the `_testimonials` folder. Take a look at the existing testimonials for the correct formatting and YAML frontmatter.

## Code snippet/examples

The code examples in the "code snippet carousel" are kept as individual markdown files in the `_snippets` folder. Please check the structure of existing snippets if you'd like to add a new one.

The "code content" is in the YAML frontmatter and requires the "literal scalar block style", i.e. start with a `|` character, and indent the code block by four spaces.

Note also the use of an excerpt separator `<!--more-->`. This is to ensure that only the content above that separator will appear on mobile (due to space constraints).

Example:

    ---
    order: 0
    title: HelloWorld.fs
    excerpt_separator: <!--more-->
    code: |
        let hello name =
            printfn $"Hello, {name}!"

        hello "github"
    ---
    ## I am the title

    I am the introdoctory paragraph. Mobile and desktop users can see me.
    <!--more-->
    - **Desktop users** can see this extra content
    - **Mobile users** will miss out

    Not ideal, but oh well.

## Developing locally

The easiest way to get started developing this repository on your own machine is by using the supplied dev container.

### Using the Dev Container

1. Install and run [Docker](https://www.docker.com/).
2. Open the repository in [Visual Studio Code](https://code.visualstudio.com/).
3. When prompted, reopen the repository in the dev container.
4. The dev container will automatically set up the development environment.

**Summary of using a dev container:**
A dev container is a pre-configured development environment that includes all the necessary tools and dependencies. It allows you to start developing without having to manually set up your environment.

If not using VSCode, consult your preferred IDE's documentation for instructions.

You may need to run the following once to install TailwindCSS dependency:

```
npm i
```

To start the development server, run the following command:

```sh
bundle exec jekyll serve
```

Or, to enable live reloading:

```sh
bundle exec jekyll serve -l
```

The site will be available at `http://localhost:4000`

## License

Except where otherwise noted, the content on fsharp.org is licensed under the [Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)](https://creativecommons.org/licenses/by/4.0/) license.

Copyright © 2012-2025 F# contributors.
