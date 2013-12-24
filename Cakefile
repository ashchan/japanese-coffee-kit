{print} = require 'util'
{spawn} = require 'child_process'

task 'build', 'Compile source', ->
  options = ['-c', '-o', 'lib', 'src']
  coffee = spawn 'coffee', options
  coffee.stderr.on 'data', (data) -> process.stderr.write data.toString()
  coffee.stdout.on 'data', (data) -> print data.toString()
  coffee.on 'exit', (code) -> callback?() if code is 0
