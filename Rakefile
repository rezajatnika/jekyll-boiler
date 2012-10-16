# Rakefile for jekyll-boiler use rake -T to list tasks

# Default task
task :default => :build

# Clean up generated site in _site folder, rake clean
desc 'Clean up generated site'
task :clean do
  clean
end

# Generate site to _site folder, rake build
desc 'Build site with Jekyll'
task :build do
  compass
  jekyll
end

# Create a new post, rake post[post-title]
desc 'Make a new post'
task :post, [:name] do |t, args|
  if args.name then
    template(args.name)
  else
    puts "Name required"
  end
end

def clean
  sh 'rm -rf _site'
  sh 'rm -rf .sass-cache'
end

def compass(opts='')
  sh 'compass compile -c config.rb --force ' + opts
end

def jekyll(opts = '')
  sh 'jekyll ' + opts
end

def template(name)
  t = Time.now
  contents = "" # otherwise using it below will be badly scoped
  File.open("_posts/yyyy-mm-dd-template.markdown", "rb") do |f| contents = f.read
  end

  contents = contents.sub("%date%", t.strftime("%Y-%m-%d %H:%M:%S %z")).sub("%title%", name)
  filename = "_posts/" + t.strftime("%Y-%m-%d-") + name.downcase.gsub( /[^a-zA-Z0-9_\.]/, '-') + '.markdown'

  if File.exists? filename then
    puts "Post already exists: #{filename}"
    return
  end
  
  File.open(filename, "wb") do |f|
    f.write contents
  end
  puts "created #{filename}"
end
