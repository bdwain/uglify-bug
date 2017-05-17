## Demo of bug in uglify or babel-polyfill or chrome

By adding babel-polyfill to the standard create-react-app app, a bug is caused in chrome 51 (no other versions seem to be affected). It onkly happens in production mode (yarn build, not yarn start). If the uglify js plugin is commented out, the bug does not happen.

in the console:

expected output:

    let str = 'fooBar'
    str.split(/(?=[A-Z])/)

    > ["foo", "Bar"]

actual output:

    let str = 'fooBar'
    str.split(/(?=[A-Z])/)

    > ["fooBar"]
