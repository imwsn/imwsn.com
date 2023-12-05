# Copyright

Content copy right belongs to owner of imwsn.com from 2023.


# Site

This site is built based on [console](https://github.com/b2a3e8/jekyll-theme-console)

## Modifications

1. Support category, created category template `_layout/category.html`, both `notes` and `thoughts` are extended
from it;
2. Pagination on homepage, added plugin `jekyll-paginate`, check [here](https://pages.github.com/versions/) for all jekyll plugins github page supports.
   - pagination under `./blog/`, pagination layout by `./blog/index.html`.


## Build locally
1. Install ruby locally
   folllow instructions from [rbenv](https://github.com/rbenv/rbenv)
2. Install `bundler` and `jekyll`, and do `bundle install`
3. Start local server

```
bundle exec jekyll serve --host=0.0.0.0
```

