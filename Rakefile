require 'rubygems'
require 'bundler'
begin
  Bundler.setup(:default, :development)
rescue Bundler::BundlerError => e
  $stderr.puts e.message
  $stderr.puts "Run `bundle install` to install missing gems"
  exit e.status_code
end
require 'rake'

require 'jeweler'
Jeweler::Tasks.new do |gem|
  # gem is a Gem::Specification... see http://docs.rubygems.org/read/chapter/20 for more options
  gem.name = "rspec-set"
  gem.homepage = "http://github.com/pcreux/rspec-set"
  gem.license = "MIT"
  gem.summary = %{set() is a helper for RSpec which setup active record
    objects before all tests and restore them to there original state 
    before each test}
  gem.description = %{set() is a helper for RSpec which setup active record
    objects before all tests and restore them to there original state 
    before each test}
  gem.email = "pcreux@gmail.com"
  gem.authors = ["Philippe Creux"]
  # Include your dependencies below. Runtime dependencies are required when using your gem,
  # and development dependencies are only needed for development (ie running rake tasks, tests, etc)
  gem.add_runtime_dependency 'rspec', '>= 2'
  #  gem.add_development_dependency 'rspec', '> 1.2.3'
end
Jeweler::RubygemsDotOrgTasks.new

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/test_*.rb'
  test.verbose = true
end

require 'rcov/rcovtask'
Rcov::RcovTask.new do |test|
  test.libs << 'test'
  test.pattern = 'test/**/test_*.rb'
  test.verbose = true
end

task :default => :test

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "rspec-set #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end

# task :setup
# git clone rspec-rails in /tmp
# in /tmp run rake clobber generate etc
#
# task :default
# run cukes
#
# features/support/env.rb should load tmp/rspec-rails...../env.rb :)
