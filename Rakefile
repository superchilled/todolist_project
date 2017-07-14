require "rake/testtask"
require "find"
require "bundler/gem_tasks"

desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

desc 'Run tests'
task :default => :test

Rake::TestTask.new(:test) do |t|
  t.libs << "test"
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']
end

desc 'List all non-dot-files'
task :list_non_dot_files do
  files = []

  Find.find(".") do |file|
    next if file.include?('/.')
    if File.file?(file)
      files << file
    end
  end

  files.each { |file| puts file }
end
