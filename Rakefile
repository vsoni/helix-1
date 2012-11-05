require 'rubygems'
require 'rake'
require 'rake/clean'
require 'rdoc/task'
require 'rspec/core/rake_task'

task :rebuild_gem do
  `sudo gem uni helix`
  `gem build helix.gemspec`
  `sudo gem i helix-*.gem`
end

RSpec::Core::RakeTask.new(:spec)
task :default => :spec

Rake::RDocTask.new do |rd|
  rd.rdoc_dir = "rdoc_html"
  rd.rdoc_files.include("lib/**/*.rb")
  rd.rdoc_files.exclude("**/*test*")
  rd.rdoc_files.exclude('multipart.rb')
end

