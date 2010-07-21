require 'rubygems'
require 'rake'


begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name                  = "tk-win"
    gem.summary               = %Q{RubyTk bindings for MS Windows RubyInstaller 1.9.1 bundled with binaries.}
    gem.description           = %Q{RubyTk bindings for windows bundled with tcltklib.so and tkutil.so for windows RubyInstaller 1.9.1}
    gem.email                 = "elia.schito@gmail.com"
    gem.homepage              = "http://www.dumbo.ai.kyutech.ac.jp/nagai/RubyTk/?Ruby%2FTk-Kit"
    gem.authors               = ["Hidetoshi Nagai", "Elia Schito"]
    
    gem.required_ruby_version = "~> 1.9.1"
    gem.platform              = "x86-mingw32"
    gem.require_paths        += Dir["lib/#{gem.platform}"]
    gem.files                += Dir["lib/#{gem.platform}/*.so"]
    
    gem.add_development_dependency "rspec", "~> 1.2.9"
    # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
  end
  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "Jeweler (or a dependency) not available. Install it with: gem install jeweler"
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

task :spec => :check_dependencies

task :default => :spec

require 'rake/rdoctask'
Rake::RDocTask.new do |rdoc|
  version = File.exist?('VERSION') ? File.read('VERSION') : ""

  rdoc.rdoc_dir = 'rdoc'
  rdoc.title = "tk-win #{version}"
  rdoc.rdoc_files.include('README*')
  rdoc.rdoc_files.include('lib/**/*.rb')
end
