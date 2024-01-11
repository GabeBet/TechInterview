# techinterview

First, I started by adding a .eslintrc.js file to fix the linter errors with the plugin:vue.base to enable the correct ESLint parsing and with babel-eslint so babel code works with ESLint.
After the linter errors were fixed, I fixed a missing } in the router/index.js file. I ran into problems trying to running the web app and looking up the error, I realized I needed to 
downgrade Node JS to version 16 and that fixed the issue. I added a router link in the app bar to the /data page and used a table icon as the button. I also added router links to the Vuetify logo
and title to return to the home page. I used the Beers data from the random data api site and fetched 25 items from it and stored it in a tableData array. I wrote down all the headers from the data and 
added them to a headers array and sent that plus the data to the Data Table component. I added a search variable in data then double binded it to a text field and to the search prop in the Data Table component. Finally I made the container holding the table fluid and set the card width to max.