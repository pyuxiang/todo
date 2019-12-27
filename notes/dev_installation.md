# Installation

For Windows 10 Pro 64-bit (Version 10.0.17763), CPU i7-8550U.

## Packages

### Ruby on Rails
`Requirements: yarn`

An open-source server-side web application framework.
Official installation guide provided by [Rails](https://guides.rubyonrails.org/getting_started.html#installing-rails). Guide to installation of SQLite3 found in [SO](https://stackoverflow.com/a/16524605).

1. Install Ruby.
    + Download Ruby installer from [Ruby website](https://rubyinstaller.org/downloads/), i.e. `Ruby+Devkit 2.6.5-1 (x64)`.
    + Verify installation with `ruby --version`.
2. Install SQLite3.
    + Download SQLite3 dll from [SQLite website](https://www.sqlite.org/download.html), i.e. `sqlite-dll-win64-x64-3300100.zip`.
    + Unpack the dll and add to PATH.
    + Download SQLite3 C source code, i.e. `sqlite-amalgamation-3300100.zip`.
    + Unpack and merge source with SQLite3 dll directory, i.e. `[SQLite3DIR]`.
    + Run `gem install sqlite3 --platform=ruby -- --with-sqlite3-dir=[SQLite3DIR] --with-sqlite3-include=[SQLite3DIR] --with-sqlite3-lib=[SQLite3DIR]`.
3. Install Rails.
    + On the command line, call `gem install rails`.
    + Verify installation with `rails --version`.

We perform a sanity check to ensure basic Rails functionality is supported.

4. Create first application using `rails new blog`.
    + Install `yarn` if `Yarn not installed` error occurs.
5. Run server using `ruby bin\rails server` from inside the blog directory.
    - Install `webpacker` with the command `rails webpacker:install` to resolve `webpacker configuration file not found` error.
6. Access [port 3000](http://localhost:3000/) on the localhost and ensure the Rails installation success landing page is served.


### Yarn
`Requirements: node`

Yarn is a package manager for Javascript libraries, replacing npm (Node Package Manager).

1. Download installer from [offical website](https://yarnpkg.com/lang/en/docs/install/#windows-stable), i.e. `yarn-1.21.1.msi`.
2. Verify yarn has been installed with `yarn --version`.


### Node.js

`Requirements: -`

A cross-platform Javascript runtime environment to execute JS code outside of a browser.
It was intended as a server-side language.
Installation steps not documented. Refer to [official website](https://nodejs.org/en/) for installation binaries.

### Mermaid

`Requirements: yarn, npm`

A script that can render Gantt charts, for project management purposes. Install with `yarn add mermaid`, as well as its optional CLI for file exports using `npm install -g mermaid.cli`. The packages cannot be installed locally for some reason.

Alternatively, use Atom's [Mermaid Preview](https://atom.io/packages/atom-mermaid).
