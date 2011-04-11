require 'rake'
require 'charleston/tasks'

task 'default' => 'generate:all'
# add custom rakefile tasks here

task 'commit-output'=>'generate:all' do
  Dir.chdir 'output' do
    sh 'git add -A'
    sh 'git commit -m "committing output"'
  end
end
