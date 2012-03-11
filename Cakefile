fs            = require 'fs'
{print}       = require 'util'
{spawn, exec} = require 'child_process'

# ANSI Terminal Colors
bold = '\033[0;1m'
green = '\033[0;32m'
reset = '\033[0m'
red = '\033[0;31m'

log = (message, color, explanation) ->
  console.log color + message + reset + ' ' + (explanation or '')

build = (watch, callback) ->
  if typeof watch is 'function'
    callback = watch
    watch = false
  options = ['-c', '-b', '-o', 'lib', 'src']
  options.unshift '-w' if watch

  coffee = spawn 'coffee', options
  coffee.stdout.on 'data', (data) -> print data.toString()
  coffee.stderr.on 'data', (data) -> log data.toString(), red
  coffee.on 'exit', (status) -> callback?() if status is 0

test = (callback) ->
  options = []
  test = spawn 'mocha', options
  test.stdout.on 'data', (data) -> print data.toString()
  test.stderr.on 'data', (data) -> log data.toString(), red
  test.on 'exit', (status) -> callback?() if status is 0


task 'docs', 'Generate annotated source code with Docco', ->
  fs.readdir 'src', (err, contents) ->
    files = ("src/#{file}" for file in contents when /\.coffee$/.test file)
    docco = spawn 'docco', files
    docco.stdout.on 'data', (data) -> print data.toString()
    docco.stderr.on 'data', (data) -> log data.toString(), red
    docco.on 'exit', (status) -> callback?() if status is 0


task 'build', ->
  build -> log ":)", green

task 'watch', ->
  build true, -> log ":-)", green

task 'spec', 'Mocha Tests', ->
  build -> test -> log ":)", green
