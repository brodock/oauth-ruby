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

$LOAD_PATH << File.dirname(__FILE__) + '/lib'
require 'oauth'


require 'jeweler'
Jeweler::Tasks.new do |s|
  s.name = %q{oauth}
  s.version = OAuth::VERSION
  s.authors = ["Pelle Braendgaard", "Blaine Cook", "Larry Halff", "Jesse Clark", "Jon Crosby", "Seth Fitzsimmons", "Matt Sanford", "Aaron Quint"]
  s.email = "oauth-ruby@googlegroups.com"
  s.description = "OAuth Core Ruby implementation"
  s.summary = s.description
  s.rubyforge_project = %q{oauth}
  s.add_development_dependency(%q<actionpack>, [">=2.3.18"])
  s.add_development_dependency(%q<rack>, [">= 1.0.0"])
  s.add_development_dependency(%q<mocha>, [">= 0.9.8"])
  s.add_development_dependency(%q<typhoeus>, [">= 0.6"])
  s.add_development_dependency(%q<em-http-request>, [">= 0.2.10"])
  s.add_development_dependency(%q<curb>, [">= 0.6.6.0"])

  s.files.include '.gemtest'
end
Jeweler::GemcutterTasks.new

require 'rake/testtask'
Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/**/*test*.rb'
  test.verbose = true
end

Dir['tasks/**/*.rake'].each { |t| load t }

task :default => :test

require 'rdoc/task'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "oauth #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
