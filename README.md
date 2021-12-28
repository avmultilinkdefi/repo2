# GitHub Commitment Bot</h1>
This bot's code was originally inspired by [Akshay Saini](https://github.com/akshaymarch7?tab=overview&from=2021-12-01&to=2021-12-27). This program is purely for educational purposes only, do not use this script in order to gain an unfair advantage amongst developers or to pretend that your commit history is legitimate.</P>

## Installation

Use the package manager [npm](https://www.w3schools.com/nodejs/nodejs_npm.asp) from [node](https://nodejs.org/en/) in order to install the needed packages to run this script locally. ( If they are not already installed ) If you need to remake the package use the command `npm init` inside of your terminal.

```node
npm install jsonfile
npm install moment
npm install simple-git
npm install random
```

## Usage

To use the bot simply open a terminal and start the script with `node bot.js`

## License
This script is licensed under the [MIT](https://choosealicense.com/licenses/mit/) license.

## Primary Script

```JavaScript 
const jsonfile = require("jsonfile");
const moment = require("moment");
const simpleGit = require("simple-git");
const random = require("random");
const { off } = require("process");
const { FILE } = require("dns");
const FILE_PATH = './data.json';
const makeCommit = (n) => {
  if (n === 0) return simpleGit().push();
  const x = random.int(0, 54);
  const y = random.int(0, 6);
  const DATE = moment()
    .subtract(1, "y")
    .add(1, "d")
    .add(x, "w")
    .add(y, "d")
    .format();
  const data = {
    date: DATE,
  };
  console.log(DATE);
  jsonfile.writeFile(FILE_PATH, data, () => {
    simpleGit()
      .add([FILE_PATH])
      .commit(DATE, { "--date": DATE }, makeCommit.bind(this, --n));
  });
};
makeCommit(1000); 
```
