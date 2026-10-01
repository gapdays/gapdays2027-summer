This is the website for the [GAP Days](https://www.gapdays.de/gapdays2027-summer).

It is based on [Jekyll](https://jekyllrb.com/), a static website generator,
and the [hyde](https://github.com/poole/hyde/) template.

If you want to test the site on your own machine, you need to have `ruby`
and `bundler` installed. Afterwards, for the first-time setup, do this:

    git clone https://github.com/gapdays/gapdays2027-summer
    cd gapdays2027-summer
    bundle install

Now whenever you want to test the site locally, you can do this:

    bundle exec jekyll serve -l

Now open a browser on http://localhost:4000/ to see a live preview
of the site.

## Steps for new GAP Days

To create a website for a new GAP Days event, follow roughly the following
steps:

1. Copy the data of the previous GAP Days into a new repository.
   Add that repository under a suitable name at https://github.com/gapdays

2. Edit all relevant files; at the very least do the following:
    - _config.yml: update baseurl to match the name of the repository at GitHub,
      and update title, description, location and email
    - index.md
    - location.md
    - registration.md
      - the "registration_state" entry at the top (`notyet`, `open` or
        `closed`) controls what the page shows
      - update the link to the registration form
      - edit the rest of the page suitably
    - participants.md
      - This contains the list of participants, in [YAML](https://en.wikipedia.org/wiki/YAML)
        format. Basic entries look like this:

            - name: John Doe
              affiliation: University of Nowhere

         Entries can be followed by links, e.g. to slides, other PDFs, etc.

            - name: John Doe
              affiliation: University of Nowhere
              links:
                "slides": http://bit.ly/gap-worksheets2015
                "photo": ../photo/john_doe.jpg

