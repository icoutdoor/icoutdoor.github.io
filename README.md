# Outdoor Club Website
### Poster's Guide

Hi! So you're trying to make a post on the website! (Or something is broken and you're here to fix it - in which case I'm so sorry...).

## About the Site

The site is hosted for free on GitHub Pages. It uses Jekyll to handle posting and all that sort of stuff. Jekyll's docs are pretty good so if you're wondering you can check them out [here](https://jekyllrb.com/docs/).
I made the site using pure HTML with a little bit fo JS (literally just for the rotating header) so it's pretty lightweight and loads quite fast, so long as the images aren't too big.

## Adding new header images

If you add a new header image, you'll need to be sure of a few things:
1. Resolution

    Make sure the image aspect ratio is **exactly** 2048 × 863 landscape. If it's any taller / shorter it messes with things. Ideally keep it to that resolution, but so long as the aspect ratio is the same it should be OK.
2. Location

    Make sure to save it in `/img/headers`.
3. Updating

    This is the boring part. At the bottom of *every HTML page*, i.e. all the pages in the home directory and `/_layouts/default.html`, you need to add the name of the new photo. e.g. `const images =  ['boulder.JPG', 'boulder-2.JPG'];` -> `const images =  ['boulder.JPG', 'boulder-2.JPG', 'my-new-pic.JPG'];`

## Adding new posts

Thanks to Jekyll, adding posts is simple and you can (theoretically) do everything on GitHub online without needing to clone the repo.

1. Create a `.md` file in `/_posts/`

    Filename must be in the format `YYYY-MM-DD-Post-Title.md`

2. Add the front matter.

    This needs to look like this:
    ```
    ---
    layout: post
    title: "NAME OF POST HERE"
    date: DATE HERE: YYYY-MM-DD
    feat-img: FEATURED (MAIN) IMAGE, e.g. "fun-trip-2022.jpg"
    ---
    ```
    The name can be in any format you like, but include the "".
    Date must be Year-Month-Day, with no ""
    Feat-img should be the name and file extension of the main image in "". This is used to make post tile look nice.

3. Write the post

    Write the post with [standard Markdown syntax](https://www.markdownguide.org/basic-syntax). Basically adding # before a line makes it a main heading, the more # you add in a row the smaller it becomes. e.g.:

    >
    >```
    ># Main heading
    >### Small heading
    >```
    ># Main heading
    >### Small heading
    >

4. Images

    Add any images you want to `/img/posts/`. To add them into the post use `![Image Alt Text](../../../img/posts/FILENAME_HERE)`.
    The `../../../img/posts/` **IS** important

Site originally made by J Howells (Equipment Officer), Christmas 2022.