namespace :greeting do
  desc 'outputs hello to the terminal'
  task :hello do
    puts "hello from Rake!"
  end

  desc 'outputs hola to the terminal'
  task :hola do
    puts "hola de Rake!"
  end
end

desc 'opens up the terminal'
task :console => :environment do
  Pry.start
end

desc 'requires the environment rb file'
task :environment do
  require_relative './config/environment'
end

namespace :db do
  desc 'creates student table in database'
  task :migrate => :environment do
    sql = 'CREATE TABLE IF NOT EXISTS students (id INTEGER PRIMARY KEY, name TEXT, grade TEXT)'
    DB[:conn].execute(sql)
  end

  desc 'populates database with dummy data from a "seed" file'
  task :seed => :environment do
    require_relative './db/seeds'
  end
end

