# Language Guesser

This repository contains a simple Node.js project that detects the language of a user-input sentence, provided the sentence meets a minimum length requirement.

## Features
Accepts user input via the command line.
Checks if the input sentence meets the minimum length requirement.
Detects and returns the language of the sentence.

## Requirements
Node.js
franc library
lang library

## Installation
Clone the repository:

bash
Copy code
git clone https://github.com/yourusername/language-detector.git
cd language-detector
Install the required dependencies:

bash
Copy code
npm install
Usage
Run the script:

bash
Copy code
node index.js
Follow the on-screen instructions to input a sentence. Ensure that the sentence meets the minimum length requirement (e.g., 10 characters).

Example
bash
Copy code

$ node index.js Bonjour tout le monde!
Our best guess is: French
Code Overview
index.js
This script contains the following functions:

``` node
import { franc } from 'franc';
import langs from 'langs';
import colors from 'colors';
 
//get input from user
const input = process.argv[2];
const langCode = franc(input);

// create error code if langauge not detected
if (langCode === 'und') {
  console.log(colors.red("SORRY, COULDN'T FIGURE IT OUT! TRY WITH MORE SAMPLE TEXT!"));
} else {
  const language = langs.where("3", langCode);
  console.log(colors.green(`Our best guess is: ${language.name}`));
}
```

Contributing
Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.


