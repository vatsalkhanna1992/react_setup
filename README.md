# react_setup
React.js environment setup and installation

### Run the following commands in your terminal:

1. mkdir react-setup

2. cd react-setup

3. npm init

4. npm install webpack webpack-dev-server --save-dev

5. npm install babel-core babel-loader babel-preset-es2015 --save-dev

6. npm install --save react react-dom

7. npm install --save-dev babel-preset-react babel-preset-stage-3

8. npm run buid

### Create index.html file:
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>React v15.4.2 ES6 Environment</title>
</head>
<body>
  <div id="app"></div>
  <script type="text/javascript" src="bundle.js"></script>
</body>
</html>

### Create one file in root directory called .babelrc:
{
  "presets": ["es2015", "react", "stage-3"]
}


### Your package.json file should look like this:-
{
  "name": "react-environment",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "build": "webpack-dev-server"
  },
  "author": "Vatsal Khanna",
  "license": "ISC",
  "devDependencies": {
    "babel-core": "^6.24.0",
    "babel-loader": "^6.4.1",
    "babel-preset-es2015": "^6.24.0",
    "babel-preset-react": "^6.23.0",
    "babel-preset-stage-3": "^6.22.0",
    "webpack": "^2.3.2",
    "webpack-dev-server": "^2.4.2"
  },
  "dependencies": {
    "react": "^15.4.2",
    "react-dom": "^15.4.2"
  }
}



### Configure webpack.config.js file in a root directory:
module.exports = {
    entry: './app/main.js',
    output: {
        filename: 'bundle.js'
    },
    module: {
        loaders: [
            {
                loader: 'babel-loader',
                test: /\.js$/,
                exclude: /node_modules/
            }
        ]
    },
    devServer: {
        port: 3000
    }
};
