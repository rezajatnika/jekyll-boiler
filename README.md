# jekyll-boiler
Base template for [Jekyll](http://jekyllrb.com/) with [HTML5 Boilerplate](http://html5boilerplate.com/).

## Usage
Clone this repository:
```
$ git clone https://github.com/jreza/jekyll-boiler.git myblog
$ cd myblog
$ rm -rf .git
```
Install required gems using bundler:
```
$ bundle install
```
To build site with Jekyll:
```
$ rake build
```
Start localhost server:
```
$ jekyll --server
```

## Rakefile Task
I've only added two tasks, use `rake -T` to list them:

```
rake build		# Build site with Jekyll
rake post[name]	# Make a new post
```

## Configuration
See `_config.yml` for configurations.