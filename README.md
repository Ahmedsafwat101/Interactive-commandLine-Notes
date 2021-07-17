
# Project Title

A brief description of what this project does and who it's for

  
## Badges


[![MIT License](https://img.shields.io/apm/l/atomic-design-ui.svg?)](https://github.com/tterb/atomic-design-ui/blob/master/LICENSEs)

  
## Features

- Add Note
- Remove Note
- List All Notes
- Read Specific Note

  
## Screenshots

![App Screenshot](https://github.com/Ahmedsafwat101/Interactive-commandLine-Notes/blob/main/imgs/npm.jpg)

![App Screenshot](https://github.com/Ahmedsafwat101/Interactive-commandLine-Notes/blob/main/imgs/Add.jpg)

![App Screenshot](https://github.com/Ahmedsafwat101/Interactive-commandLine-Notes/blob/main/imgs/remove.jpg)

![App Screenshot](https://github.com/Ahmedsafwat101/Interactive-commandLine-Notes/blob/main/imgs/read.jpg)

![App Screenshot](https://github.com/Ahmedsafwat101/Interactive-commandLine-Notes/blob/main/imgs/list.jpg)


  
## Tech Stack

**Client:** JS

**Server:** Node

  
## Usage/Examples

```javascript
const yargs = require('yargs')
const notes = require('./notes.js')

// Create add command
yargs.command({
    command: 'add',
    describe: 'Add a new note',
    builder: {
        title: {
            describe: 'Note title',
            demandOption: true,
            type: 'string'
        },
        body: {
            describe: 'Note body',
            demandOption: true,
            type: 'string'
        }
    },
    handler(argv) {
        notes.addNote(argv.title, argv.body)
    }
})

// Create remove command
yargs.command({
    command: 'remove',
    describe: 'Remove a note',
    builder: {
        title: {
            describe: 'Note title',
            demandOption: true,
            type: 'string'
        }
    },
    handler(argv) {
        notes.removeNote(argv.title)
    }
})

// Create list command
yargs.command({
    command: 'list',
    describe: 'List your notes',
    handler() {
        notes.listNotes()
    }
})

// Create read command
yargs.command({
    command: 'read',
    describe: 'Read a note',
    builder: {
        title: {
            describe: 'Note title',
            demandOption: true,
            type: 'string'
        }
    },
    handler(argv) {
        notes.readNote(argv.title)
    }
})

yargs.parse()
```

  
## Running Tests

To run tests, run the following command

```bash
  node script.js help
  node script.js add --title="DataStructure Exam" --body="The exam will be on Monday instead of Sunday"
  node script.js remove --title="DataStructure Exam" --body="The exam will be on Monday instead of Sunday"
  node script.js read --title="Schedule a Mock Interview"
  node script.js list
```

  
## Run Locally

Clone the project

```bash
  git clone https://github.com/Ahmedsafwat101/Interactive-commandLine-Notes
```

Go to the project directory

```bash
  cd my-project
```

Install dependencies

```bash
  npm install
```

Start the server

```bash
  npm run start
```

  

  
## Dependencies
- Yargs
- Chalk
- fs
  
