# New report checklist/guidance

These are a WIP and may be missing steps. Please update with additional info!

1. For a new report click `use this template` on github.com. Give it a title with the report number.
2. Clone the new repo to work locally -- use Dev mode to see how changes will look live (instructions below).
4. Add report figures to the `out/figures` directory  
   - Links to figures are formatted as `![Figure caption](fig_name.png)`
3. Write report in markdown in the `src` directory
   - Update the `00-frontmatter.md` with the report cover image name and intro blurb
5. Once report is finalized, create a PDF version
   - locally, run `node build_pdf.js` in the terminal 
   - PDF is created under `out/PDF_Report_Title.pdf` (see below for details)
   - Add PDF link to `src/00-frontmatter.md` with the following template: 
   ```html
   <a href="/PDF_Report_Title.pdf" target="_blank" id="report-pdf-download">download the PDF</a>
   ```
6. Generate a new property in Google Analytics and update `build_html.js` with the associated tracking ID. The new property must be of the (older) "universal analytics" type, which can be found in the advanced options when creating a new property (itself found in the admin pane). You do not need to create both a universal analytics and v4 property, just universal analytics.
7. Update the `build_html` with report metadata 
7. Deploy the report (make it live!). See instructions below. 
8. Update our FastForwardLabs blog with new Report link. See instructions [here.](https://github.com/fastforwardlabs/blog#adding-a-report-link)

# Dev

Report repository template -- we use markdown now. Write markdown in the `src` directory. See `src/00a-example.md` for how to format.

To run locally, make sure you have nodejs and NPM installed and then do:

```
npm install
npm run dev
```

# Deploy

To deploy you can clone the repo make sure you have nodejs and NPM installed and do:

```
npm install
npm run deploy
```

You should also commit and push your changes (like normal) to the repo.
By default, the page will go live at fastforwardlabs.github.io/repo-name.
Once a custom domain has been procured (only Chris and Sean Browne can do this), you can point to it by editing `out/CNAME` to include a single line with just the domain name. For instance the whole file would read: `a-cool-custom-domain.fastforwardlabs.com`.

# General info (for debugging)

This is a node app. All of the logic to build the report is contained in the `build_html.js` file. It uses a markdown parser called `markdown-it`, if you're having markdown problems you can look at the docs for that package. It also uses several plugins for extra markdown functionality (like footnotes), you can see those plugins in the file and look up the package online to debug/figure out options.

It is definitely not the most cleanly organized file, the CSS especially is distributed a bit confusingly. But the good news is there is no outside magic (besides the markdown parser) everything used to build the report is in that file.

Mostly for new reports you'll use edit markdown files in `src`, but there are a few things hardcoded into the `build_html` file: the meta tags for social links and the google analytics code (to find them just search the file for 'meta' and 'google'). You'll need to change those in the build file in the report repo directly.

There is also the `build_pdf.js` file which will generate a PDF of the report. You need to run this file manually when you want to generate a pdf (`node build_pdf.js`). You can change the file name generated in the build file itself (it is not a big file).

## About dev

Like I said, the main part of this script is the `build_html.js` script. The `dev` command, defined in `package.json` uses several packages to automatically reload changes in the browser as you make them. Those packages may break at some point, or have compatibility issues. If that happens, you might want to look for different packages with the reload functionality -- there's nothing special about the ones being used currently.

## About deploy

The deploy script is also in `package.json`, it uses a package to deploy to the gh-pages branch. You can set a custom domain name in the settings tab on github.

