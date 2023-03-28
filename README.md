# Outdoor Club Website
### Poster's Guide

Hi! So you're trying to make a post on the website! (Or something is broken and you're here to fix it - in which case I'm so sorry...).

## About the Site

The site is hosted for free on GitHub Pages. It uses Jekyll to handle posting and all that sort of stuff. Jekyll's docs are pretty good so if you're wondering you can check them out [here](https://jekyllrb.com/docs/).
I made the site using pure HTML with a little bit fo JS (literally just for the rotating header) so it's pretty lightweight and loads quite fast, so long as the images aren't too big.

## Adding new posts

Thanks to Jekyll, adding posts is simple and you can (theoretically) do everything on GitHub online without needing to clone the repo.

1. Create a `.md` file in `/_posts/`

    Filename must be in the format `YYYY-MM-DD-Title.md`
    The title can be anything sensible but the date is important to make sure the posts are displayed in the right order.

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

## Events

Especially for fresher season, it's super important to have an up-to-date list of events on the website. To add events, add a new file to the `/_events/` folder. Like with the posts, it should be a `.md` file, but the front matter for Jekyll looks a bit different. Here's an example for a Westway session:
```
---
name: "Westway"
event-date: "Mondays"
event-time: "6-8pm"
description: "Westway is the best climbing centre with rope climbing in our part of London. Come along with Outdoor Club every other Monday - whether beginner or seasoned pro!"
---
```

*The order the events are displayed in depends on filename, not date. Make sure to number them sensibly.*

The important things are:
- Start and end the file with `---`
- Add a short event name after `name:`
- `event-date:` can be an actual date ('June 3rd') or something more general ('Thursdays')
- `event-time:` can again be specific or general ('7:30pm' or 'Afternoon')
- `description:` should be a short description of the event.
- **All** of these fields should be filled out or the website will have weird blanks

## Committee page

Each committee member should have a square photo (i.e. width = height) added to the `/img/committee/` directory. They should be in the JPEG file format, and should be named after the position name (see the current ones: `president.jpeg` for Pres, `qm.jpeg` for Quartermaster etc).
You can then update the names and blurbs (keep them short) of the committee members in the `/_committee` folder. Don't change the filenames or any of the metadata in the files, only change the `name:` and `blurb:` fields. The committee page should update automatically.

## Adding new header images

If you add a new header image, you'll need to do a few things:
1. Resolution

    Make sure the image aspect ratio is **exactly** 2048 × 863 landscape. If it's any taller / shorter it messes with things. Ideally keep it to that resolution, but so long as the aspect ratio is the same it should be OK.
2. Location

    Save the new image in `/img/headers`.
3. Updating

    You now need to add the header to the list of headers. Go to `/_includes/footer.html`, and find `const images` (it's currently on line 12, but this might've changed if the file has been updated.)
    Add the name of the new photo. e.g. `const images =  ['boulder.JPG', 'boulder-2.JPG'];` becomes `const images =  ['boulder.JPG', 'boulder-2.JPG', 'my-new-pic.JPG'];`

Site originally made by J Howells (Equipment Officer), Christmas 2022.
