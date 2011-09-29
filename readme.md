# Cakefile Template

If you write a lot of coffeescript and get tired of 
setting up your build, watch and spec tasks, grab this 
Cakefile and put it in your project.

# Install

```
npm install get-post -g

# nav to your project folder

get https://raw.github.com/twilson63/cakefile-template/master/Cakefile >> Cakefile

```
# Usage

## Compiling

Put all of your coffee-script in the src folder, it will compile all coffee-script
in your lib folder, using the build command.

```
cake build
```

## Watching 

If you want to compile as you write your code, invoke the watch command.

```
cake watch
```

## Testing

If you want to run your spec tests, assuming you are using jasmine-node.

```
cake spec
```

## Documenting

```
cake docs
```

Have Fun! 
