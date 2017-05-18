## Demo of bug in uglify reduce_vars option

Index.js contains the source of babel-polyfill. The build minfies it with the reduce_vars option enabled. This causes a bug in chrome 51 (no other versions seem to be affected). 

in the console:

expected output:

    let str = 'fooBar'
    str.split(/(?=[A-Z])/)

    > ["foo", "Bar"]

actual output:

    let str = 'fooBar'
    str.split(/(?=[A-Z])/)

    > ["fooBar"]
