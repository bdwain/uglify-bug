## Demo of bug in uglify or webpack uglify plugin or babel-polyfill or chrome

I started with create-react-app's canary build (because it needs webpack 2 to reproduce the issue). 

    create-react-app my-app --scripts-version react-scripts@canary

By importing babel-polyfill in the entry point, a bug is caused in chrome 51 (no other versions seem to be affected). It only happens in production mode (yarn build, not yarn start). If the uglify js plugin is commented out, the bug does not happen.

in the console:

expected output:

    let str = 'fooBar'
    str.split(/(?=[A-Z])/)

    > ["foo", "Bar"]

actual output:

    let str = 'fooBar'
    str.split(/(?=[A-Z])/)

    > ["fooBar"]
