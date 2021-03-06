source :rubygems
source :rubyforge
source :gemcutter

gem 'bundler', '~> 1.0.0'
gem 'rails', '2.3.11'
gem 'rack' , '~> 1.1.1'
gem 'i18n', '>= 0.4.2'
gem 'rubytree', '0.5.2', :require => 'tree'
gem 'coderay', '~> 0.9.7'

group :development do
end

group :production do
end

group :test do
  gem 'shoulda', '~> 2.10.3'
  gem 'mocha'
  gem 'edavis10-object_daddy', :require => 'object_daddy'
end

group :openid do
  gem "ruby-openid", '~> 2.1.4', :require => 'openid'
end

group :rmagick do
  gem "rmagick", "~> 1.15.17"
end

# Use the commented pure ruby gems, if you have not the needed prerequisites on
# board to compile the native ones.  Note, that their use is discouraged, since
# their integration is propbably not that well tested and their are slower in
# orders of magnitude compared to their native counterparts. You have been
# warned.
#
platforms :mri do
  group :mysql do
    gem "mysql"
    #   gem "ruby-mysql"
  end

  group :mysql2 do
    gem "mysql2", "~> 0.2.7"
  end

  group :postgres do
    gem "pg", "~> 0.9.0"
    #   gem "postgres-pr"
  end

  group :sqlite do
    gem "sqlite3-ruby", "< 1.3", :require => "sqlite3"
    #   please tell me, if you are fond of a pure ruby sqlite3 binding
  end
end

platforms :mingw do
  group :mysql do
    gem "mysql"
    #   gem "ruby-mysql"
  end

  ## Add Windows support
  ## https://github.com/brianmario/mysql2/issues/8
  ## Getting mysql2 gem to work with Ruby on Rails 3.0 and Windows 7 64bit 
  ## http://paul-wong-jr.blogspot.com/2011/06/getting-mysql2-gem-to-work-with-ruby-on.html
  # group :mysql2 do
  #   gem "mysql2", "~> 0.2.7"
  # end

  group :postgres do
    gem "pg", "~> 0.9.0"
    #   gem "postgres-pr"
  end
 
  group :sqlite do
    gem "sqlite3-ruby", "< 1.3", :require => "sqlite3"
    #   please tell me, if you are fond of a pure ruby sqlite3 binding
  end
end

platforms :jruby do
  gem "jruby-openssl"

  group :mysql do
    gem "activerecord-jdbcmysql-adapter"
  end

  group :postgres do
    gem "activerecord-jdbcpostgresql-adapter"
  end

  group :sqlite do
    gem "activerecord-jdbcsqlite3-adapter"
  end
end

# Load plugins Gemfiles
Dir.glob(File.join(File.dirname(__FILE__), %w(vendor plugins * Gemfile))) do |file|
  puts "Loading #{file} ..." if $DEBUG # `ruby -d` or `bundle -v`
  instance_eval File.read(file)
end
