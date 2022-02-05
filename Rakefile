require 'rake/testtask'
require 'find'
require 'pry'
require 'bundler/gem_tasks'

desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

desc 'Run tests'
task :default => :test

Rake::TestTask.new(:test) do |t|
  t.libs << 'test'
  t.libs << 'lib'
  t.test_files = FileList['test/**/*_test.rb']
end

# List all files which do not start with a '.', and are not located in a
# directory whose name starts with '.'
desc 'List unhidden files'
# Book solution
task :list_files do
  Find.find('.') do |path|
    next if path.include?('/.')
    puts path if File.file?(path)
  end
end
# My Solution
# task :list_files do
#   Find.find('.') do |path|
#     next if path == '.'
#     if File.directory?(path)
#       if File.basename(path).start_with?('.')
#         Find.prune
#       else
#         next
#       end
#     elsif File.file?(path)
#       name = File.basename(path)
#       puts name unless name.start_with?('.')
#     end
#   end
# end
