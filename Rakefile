require 'rubygems'
require 'rake'

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "postgis_adapter"
    gem.summary = "PostGIS Adapter for Active Record"
    gem.description = "Execute PostGIS functions on Active Record"
    gem.email = "x@nofxx.com"
    gem.homepage = "http://github.com/nofxx/postgis_adapter"
    gem.authors = ["Marcos Augusto"]
    gem.rubyforge_project = "postgis_adapter"
    # TODO: better way for this.....
    #    gem.add_dependency 'geo_ruby'
    # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
  end
rescue LoadError
  puts "Jeweler not available. Install it with: sudo gem install technicalpickles-jeweler -s http://gems.github.com"
end

require 'spec/rake/spectask'
Spec::Rake::SpecTask.new(:spec) do |spec|
  spec.libs << 'lib' << 'spec'
  spec.spec_files = FileList['spec/**/*_spec.rb']
end

Spec::Rake::SpecTask.new(:rcov) do |spec|
  spec.libs << 'lib' << 'spec'
  spec.pattern = 'spec/**/*_spec.rb'
  spec.rcov = true
end
task :default => :spec

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  config = YAML.load(File.read('VERSION.yml'))
  version = "#{config[:major]}.#{config[:minor]}.#{config[:patch]}"

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "postgis_adapter #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
