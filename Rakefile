require 'rubygems'

require 'rake'
require 'rake/clean'
require 'rake/rdoctask'
require 'spec/rake/spectask'
require 'rake/gempackagetask' 

require './lib/recurrence.rb'

CLEAN << 'doc' << 'pkg'

task :default => [:spec]
 
desc "Run all specs"
Spec::Rake::SpecTask.new('spec') do |t|
  t.spec_opts = ['--colour --format specdoc --loadby mtime --reverse']
  t.spec_files = FileList['spec/*_spec.rb']
end

desc "Create RDoc"
Rake::RDocTask.new('doc') do |rd|
  rd.rdoc_dir = 'doc'
  rd.options << '--title' << 'Recurrence' << '--charset' << 'utf-8' << '--inline-source' << '--line-numbers' << '--main' << 'README'
  rd.rdoc_files.include('README', 'MIT-LICENSE', 'lib/**/*.rb')
end
