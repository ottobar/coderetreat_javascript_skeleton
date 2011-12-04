Coderetreat Javascript Skeleton
===============================
This meant to be a ready-to-use environment for a paring session during a
Coderetreat, using JavaScript and/or CoffeeScript with Jasmine.

Prerequisites
-------------
* Qt for jasmine-headless-webkit `brew install qt --build-from-source`
  (takes an hour or so to build)

Setup
-----
Install the gem dependencies with:

    bundle install

And then start Guard:

    bundle exec guard

Using with CoffeeScript
-----------------------
When it compiles to JavaScript, all CoffeeScript is wrapped in an
anonymous function. Therefore, in order for a class to be accessible
by the Jasmine spec, it needs to be attached to the global window
object. For example:

spec/CellSpec.coffee

    describe "Cell", ->
      cell = new Cell()
      
      it "does stuff", ->
        expect(cell.does()).toEqual('stuff')

lib/Cell.coffee

    class Cell
      does: ->
        'stuff'

    window.Cell = Cell