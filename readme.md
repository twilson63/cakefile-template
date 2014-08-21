# Cakefile Template

If you write a lot of coffeescript and get tired of 
setting up your build, watch and spec tasks, grab this 
Cakefile and put it in your project.

# Install

```bash
# In your project directory...
curl https://raw.github.com/twilson63/cakefile-template/master/Cakefile >> Cakefile
## If that does not work... try
curl https://raw.githubusercontent.com/twilson63/cakefile-template/master/Cakefile >> Cakefile

```
# Usage

## Compiling

Put all of your coffee-script in the src folder, it will compile all coffee-script
in your lib folder, using the build command.

```bash
cake build
```

## Watching 

If you want to compile as you write your code, invoke the watch command.

```bash
cake watch
```

## Testing

If you want to run your tests, assuming you are using mocha.

```bash
cake test
```

## Documenting

```bash
cake docs
```

## Options ##
If you want to generate HTML5 maps when compiling (watching), add 'm' before `compile` or `watch`:

```bash
cake -m compile
```

`clean` will also take care of mapping files. 

More information about mapping can be found on [HTML5rocks](http://www.html5rocks.com/en/tutorials/developertools/sourcemaps/) or [Coffeescript.org](http://coffeescript.org/#source-maps).


Have Fun! 
