# Commit Bot</h1>
[Akshay Saini](https://github.com/akshaymarch7?tab=overview&from=2021-12-01&to=2021-12-27) was the inspiration for this bot's code. This program is intended solely for educational purposes; do not use it to gain an unfair advantage among developers or to pretend that your commit history is legitimate.
</P>

## Installation
Install the required packages for running this script locally using the [node](https://nodejs.org/en/) package manager [npm](https://www.w3schools.com/nodejs/nodejs_npm.asp).

`node
npm install
`

## Usage

'node bot.js' can be used to launch the bot application.

## Editable Variables

The commit graph on Github can be viewed as a chart; the code below will be used to determine the placements of our commits on the chart; if you do not want it to be random, remove both the x and y constants and manually set the placements.
```JavaScript 
const x = random.int(0, 54);
const y = random.int(0, 6);
const DATE = moment()
  .subtract(1, "y")
  .add(1, "d")
  .add(x, "w")
  .add(y, "d")
  .format();
```

The bot's default commit amount is 1,000; if you want to change it, you can do so by editing the variable inside the parenthesis. Please keep in mind that stopping the script in the middle of the process will not push the commit changes, so it's best to keep it to a low number.
```JavaScript
makeCommit(1000); 
```
