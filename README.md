# Support Engineer Test

> This Rails application has been intentionally broken!

This project is based on a popular blogging platform, Publify.

### What's Publify?
You will be forking & cloning an open source (MIT LICENSE) blogging platform called Publify.

Publify is a simple but full featured web publishing software. It's built
around a blogging engine and a small message system connected to Twitter.

#### Features

- A classic multi user blogging engine
- Short messages with a Twitter connection
- Text filters (Markdown, Textile, SmartyPants, @mention to link, #hashtag to link)
- A widgets system and a plugin API
- Custom themes
- Advanced SEO capabilities
- Multilingual : Publify is (more or less) translated in English, French,
  German, Danish, Norwegian, Japanese, Hebrew, Simplified Chinese, Mexican
  Spanish, Italian, Lithuanian, Dutch, Polish, Romanian…

#### Resources

- [Publify Repo](https://github.com/publify/publify)

## Getting Started: Installing Publify Locally

To install Publify you need the following:

- [x] Ruby 2.0, 2.1, 2.2, 2.3 or 2.4
- [x] Ruby On Rails 4.2.x

- [x] A compatible JavaScript installation for asset compilation. See [the execjs readme](https://github.com/sstephenson/execjs#readme) for details.
- [X] ImageMagick

#### Setup ImageMagick Dependency
Make sure that you have ImageMagick installed (used by mini_magick).

Check for imagemagick:
```bash
$ which convert
# /path/to/bin/convert
```

Install it if it's missing (this can take a few minutes):
```bash
$ brew update
$ brew link
$ brew install imagemagick
```

#### Setup Rails Application
Fork & Clone the Publify repo:

```bash
$ bundle install
$ rake db:setup
$ rake db:migrate
$ rake db:seed
$ rails server
```

You can now launch you browser and access 0.0.0.0:3000.

You will be prompted to supply a blog title and email:

<img width="382" alt="setup blog screenshot" src="https://cloud.githubusercontent.com/assets/1489337/12763124/9cbd3a5e-c9a7-11e5-97e3-e39e6098adf3.png">

You will be signed in and issued a username and password:

<img width="380" alt="setup example login info screenshot" src="https://cloud.githubusercontent.com/assets/1489337/12763208/0440d834-c9a8-11e5-9c81-05a4b60e9722.png">

#### Seed your blog with posts & tags
Now that our blog is setup we can use the seeds again to load some data.
```bash
$ rake db:seed
# => Seeded 24 articles...
```

#### Look around!
* Visit your blog homepage at `0.0.0.0:3000/`
* Go to the `/admin` backend and poke around (it's similar to wordpress).
* Create your first blog post!

##Support Tickets

A number of issues have been added to this application. Each one is expressed in a support ticket below. 
For this assignment you will open the support ticket as indicated as a github issue in your forked
repository. Then you will make comments on this ticket about the fixes you implmented or questions you would ask
back to the submitter. Once you fix and document or ask questions, move on to the next ticket and repeat the process.

We are hoping to see how you solve problems as well as how you communicate so please be as detailed as possible in each
response.

> Remember to copy the content of each ticket below to the `issues` section of your repo before you get started.

###Support Ticket \#1: Inconsistent Sidebar Styles
The style of **Articles** on the sidebar is inconsistent with the other sidebar menu items.
Steps to reproduce: 
1. as admin login and create at least one article 
2. proceed to 0.0.0.0:3000 and view the article 
3. on the right side observe the font for Archives differs from the other headers 
4. on the right side observe that the bullet points under archives are filled circles 
Expected behavior: 
1. Archives font should be monotype 
2. Archives bullets should use unfilled-circle

###Support Ticket \#2: Post tags are shown as "object"
The list of tags associated with a given blog post always display "tags object, object, object".

Steps to reproduce:

1. Create a new post
2. When you press publish, enter some tags (quantity doesn't seem to matter)
3. Finish publishing the post
4. Visit the root route
5. Observe the newest post has tags "object object"

Expected behavior:
1. the tags one types are displayed in the article summary

###Support Ticket \#3: Sign-in form displays raw span html in input fields
The http://0.0.0.0:3000/users/sign_in page shows `<span class=` in the input fields, and other HTML "debris" below them.

Steps to reproduce:
1. logout
2. visit http://0.0.0.0:3000/users/sign_in
3. view the form fields to sign-in

Expected behavior:
1. Login field should say 'Login' (in english)
2. Password field should say 'Password' (in english)

###Support Ticket \#4: Top Month Always Empty (Archive Sidebar)
* When I click on the top-most month in the Archive Sidebar it says "No posts found...".

Steps to reproduce:
1. Visit http://0.0.0.0:3000
2. Click on the top-most month in the Archive Sidebar
3. You will see "No posts found...". despite there being at least one post.

Expected behavior:
1. When you click on the top most month in the sidebar that has at least one post we should see that post or posts

###Support Ticket \#5: Months sorted incorrectly (Archive Sidebar)
The sort order of months in the Archive Sidebar is off, with January 2015 appearing directly above December 2015:

Steps to reproduce:
1. Visit http://0.0.0.0:3000
2. Look at the Archive Sidebar
3. January 2015 appears before December 2015

Expected behavior:
1. Date's in the Archive Sidebar should appears from most recent to oldest

## Resolving the Issue
Please fix each bug on its own branch (e.g. `fix_sidebar_styles`).

When you're finished with a bug, create a pull request that is linked to the issue your resolving to merge your branch back into the master branch.
