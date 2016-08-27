# course-website-16fa

Website for Penn's Data Structures and Algorithms course (CIS 121 Fall 2016).

Installation
------------

1. Install [Ruby](https://www.ruby-lang.org/en/) and the [Bundler
   gem](https://bundler.io). If you are using a Mac, you already have Ruby
   installed, so the following command should work (maybe needing `sudo`):

   ```
   $ gem install bundler
   ```

2. Install [NPM](https://www.npmjs.com). It is available as a Homebrew package,
   so you can just run

   ```
   $ brew install npm
   ```

   (Otherwise, follow the NPM project's instructions for your platform.)

3. Install this project's dependencies from Bundler and NPM, and check out
   submodules that this project depends on:

   ```
   $ bundle install
   $ npm install
   ```

4. Build and run the website locally. (Note that all Jekyll commands such as
   `jekyll build` or `jekyll serve` must be prefixed with `bundle exec`.)

   ```
   $ bundle exec jekyll serve --watch --incremental
   ```

   Now, navigate to [`http://localhost:4000/`](http://localhost:4000), and
   you should see the website!
