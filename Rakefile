



#namespacing our rake.. or grouping our rake 

namespace :greeting do
  desc "outputs hello to the terminal"
  task :hello do
    puts "hello from Rake!"
  end

  desc 'outputs hola to the terminal'
  task :hola do
    puts "hola de Rake!"
  end
end

task :environment do
  require_relative './config/environment'
end


namespace :db do
  desc 'migrate changes to your database'
  task migrate: :environment do 
    Student.create_table
  end
  #seeding our database  with some placeholder data 
  desc 'seed the database with some dummy data'
  task seed: :environment do
    require_relative './db/seeds'
  end
end


#we've already run rake db:migrate to create the database table i.e migrate 
#we've already inserted 5 records in the database record  i.e sseeding 

#Building a Rake task that will help us load Pry console for us 
desc 'drop into the Pry console'
task console: :environment do
  Pry.start
end
