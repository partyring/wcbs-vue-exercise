# WCBS Vue.JS Code Test by Danielle Platt

## Running

- clone directory and cd into it
- `npm i` or `npm install` to install node modules
- `npm run serve` run a webpack build which serves the website on `http://localhost:8080`.
- `npm run lint` is used for linting the code

## Acknowledgements

This is based on:

- https://gist.github.com/rlweb/e5036f1d7ae34bed42d3db67345abe56
- https://github.com/wcbs-ltd/wcbs-vue-code-test
- https://gist.github.com/rlweb/7e65ed4e0caa59d3b6e77bb006652928

## Author Notes

This project reactively updates in the UI the list of countries when editing or removing the country data; however, it does not affect the JSON file directly. Given more time, I would look into an implementation of node FS which could be used in the browser.
