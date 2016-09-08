Learning Rails
==============

I [tried this before with Android](https://github.com/cmccarty/android-big-nerd) and I liked how it went for the first month or so before I completely forgot about it. Now I'm trying it again, but this time with Rails. Yes, I should probably finish what I stared on Android first, but stop judging me.

What follows is my progress as I follow the [https://www.railstutorial.org](Rails Tutorial). I plan to tag each chapter as I add notes and sample code to keep myself diciplined and to also let anyone pick up from any point if they so wish. Here we go.

*Note: If the commit dates seem like a long time ago, it's probably a git issue and definitely not me slacking off...*

* * * 

# Notes

## Chapter 1: From zero to deploy

### Rails Commants
| command | Info | 
| ------- | ---- |
| `rails new` | creates a skeleton Rails application (and the directory, eg `rails new hello_app`).  Finishes by running `bundle install` which can install a bunch of other dependencies / libraries. |
| `rails server` | (or `rails s`) starts local server running app |

    
### Skeleton Project
| Directory | Comments |
| --------- | -------- | 
| app/ | Core application (app) code, including models, views, controllers, and helpers |
| app/assets | Applications assets such as cascading style sheets (CSS), JavaScript files, and images |
| bin/ | Binary executable files |
| config/ | Application configuration |
| db/ | Database files |
| doc/ | Documentation for the application |
| lib/ | Library modules |
| lib/assets | Library assets such as cascading style sheets (CSS), JavaScript files, and images |
| log/ | Application log files |
| public/ | Data accessible to the public (e.g., via web browsers), such as error pages |
| bin/rails | A program for generating code, opening console sessions, or starting a local server |
| test/ | Application tests |
| tmp/ | Temporary files |
| vendor/ | Third-party code such as plugins and gems |
| vendor/assets | Third-party assets such as cascading style sheets (CSS), JavaScript files, and images |
| README.md | A brief description of the application |
| Rakefile | Utility tasks available via the rake command |
| Gemfile | Gem requirements for this app |
| Gemfile.lock | A list of gems used to ensure that all copies of the app use the same gem versions |
| config.ru | A configuration file for Rack middleware |
| .gitignore | Patterns for files that should be ignored by Git |


### Gems
- `gem 'sqlite3'`: Installs the latest version
- `gem 'uglifier', '>= 1.3.0'`: Installs latest version greater than 1.3.0
- `gem 'coffee-rails', '~> 4.0.0'`: Installs latest version between 4.0.0 and 4.1 (ie sticks to that minor version range). Looks at last digit, so you could do `gem 'coffee-rails', '~> 4.0'` to limit between 4.0 and 4.1.

To find exact version for each gem, run `gem lst <gem name>`. 

### Deployment
Deploy with Heroku, which uses Postgres (not sqlite). Add gem, and then `bundle install --without production`

```ruby
group :production do
  gem 'pg', '0.18.4'
end
```

#### Login and upload SSH keys to heroku (so simple!)
```
$ heroku login
$ heroku keys:add

$ heroku create
$ heroku rename rails-tutorial-hello
```

#### Deploy
```
git push heroku master
```


### What we learned
- Ruby on Rails is a web development framework written in the Ruby programming language.
- Installing Rails, generating an application, and editing the resulting files is easy using a pre-configured cloud environment.
- Rails comes with a command-line command called rails that can generate new applications (`rails new`) and run local servers (`rails server`).
- We added a controller action and modified the root route to create a “hello, world” application.
- We protected against data loss while enabling collaboration by placing our application source code under version control with Git and pushing the resulting code to a private repository at Bitbucket.
- We deployed our application to a production environment using Heroku.


* * * 

# Resources
- [https://www.railstutorial.org/book](railstutorial.org)
- [http://railscasts.com](railscasts.com)
- [https://gorails.com](gorails.com)
- [https://www.codeschool.com/courses/rails-best-practices](rails best practices)

