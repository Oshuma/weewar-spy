def do_not_show_test_names_when_running_tests 
  Rake::TestTask.class_eval do
    alias_method :crufty_define, :define
    def define
      @verbose = false
      crufty_define
    end
  end
end

require 'rake'
require 'rake/testtask'
require 'rake/rdoctask'

do_not_show_test_names_when_running_tests

desc 'Default: run unit tests.'
task :default => :test

desc 'Test WeewarSpy.'
Rake::TestTask.new(:test) do |t|
  t.libs << 'lib'
  t.pattern = 'test/**/*_test.rb'
  t.verbose = true
end
