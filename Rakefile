require 'date'
require 'time'

namespace :new do
  desc "create post"
  task :post, [:name] do
    title = ARGV.last
    time = Time.now

    filename = time.strftime("%y-%m-%d-#{title}.markdown")
    directory = File.dirname(__FILE__) + "/_posts/"

    File.open(directory + filename, "w") do |f|
      f.puts "---"
      f.puts "layout: post"
      f.puts "title: \"#{title}\""
      f.puts "date: #{time}"
      f.puts "---"
    end

    ARGV.slice(1,ARGV.size).each{|v| task v.to_sym do; end}
  end
end
