require 'rake'
require 'charleston/tasks'

task 'default' => 'generate:all'
# add custom rakefile tasks here

namespace :output do
  desc 'Sync the output and master repos against each other.'
  task :sync=>['sync:master', 'sync:output']

  namespace :sync do
    task :master do
      sh 'git fetch output'
    end
    task :output do
      Dir.chdir 'output' do
        sh 'git fetch master'
      end
    end
  end

  task :push => :commit do
    Dir.chdir 'output' do
      sh 'git push'
    end
  end

  task :commit=>'generate:all' do
    Dir.chdir 'output' do
      sh 'git add -A'
      sh 'git commit -m "committing output"'
    end
  end
end
