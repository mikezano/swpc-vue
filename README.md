# Pre-Reqs

1. Download & Install Node.js [https://nodejs.org/en/](https://nodejs.org/en/)

   - Go with the LTS (long term support) version
   - This will set you up with NPM (node package manager)

2. You will probably need to set your proxy for npm

   - Info: [https://intelpedia.intel.com/Proxy_at_Intel](https://intelpedia.intel.com/Proxy_at_Intel)
   - You'll need to run the following commands:
   - `npm config set proxy http://proxy-chain.intel.com:911`
   - `npm config set https-proxy http://proxy-chain.intel.com:912`
   - `set HTTP_PROXY=http://proxy-chain.intel.com:911`
   - `set HTTPS_PROXY=http://proxy-chain.intel.com:912`

3. Install the [Vue Cli](https://cli.vuejs.org/)

   - `npm install -g @vue/cli`
   - This takes ~ 5min
   - You should then be able to run `vue -V` and get a version number back

4. Create a Vue project
   - `vue create <project-name>`
   - Run through set up steps
   - Add these options: (Babel, Linter/Formatter, Router, Unit Testing)
   - History mode for router ? say no
   - Select ESLint + Prettier, Lint on save
   - Choose Jest for the unit testing
   - Select 'In dedicated config files'
   - Wait for everything to install (~ 5min)
   - You should then be able to `cd` into the project folder and run `npm run serve` to launch the site.

# Resources

Use this to setup a fake json response

[https://jsonplaceholder.typicode.com/](https://jsonplaceholder.typicode.com/)

[https://my-json-server.typicode.com/](https://my-json-server.typicode.com/)

Example from my github

[https://github.com/mikezano/zson/blob/master/db.json](https://github.com/mikezano/zson/blob/master/db.json)

You can then make a fake api call like so:

[https://my-json-server.typicode.com/mikezano/zson/fruits](https://my-json-server.typicode.com/mikezano/zson/fruits)

Fonts!

[https://fonts.google.com/](https://fonts.google.com/)
