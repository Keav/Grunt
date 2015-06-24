# Grunt
Project scaffold for a Grunt based project

## Deleting the `node_modules` folder on Windows

Due to the ridiculous folder nesting associated with node modules (the nesting is how it defines dependancies) and Windows ridiculous limit on path lengths (the path cannot exceed 256 characters), Windows often has major issues deleting this folder.

RimRaf (https://github.com/isaacs/rimraf) to the rescue!

RimRaf is the UNIX command `rm -rf` (Recursive, Force).

Install it globally:
```
npm install rimraf -g
```

Then run it where you need to delete `node_modules`:
```
rimraf node_modules
```

...and breathe ;)
