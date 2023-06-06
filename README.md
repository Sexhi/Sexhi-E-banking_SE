# E-banking system

## Team Members

* Sexhi Picaku
* Stiv Daiu
* Kiara Pajova


## Tasks implemented

# data.json
The provided code is a JSON object that represents an array of bank accounts. Each account is represented as an object with several properties:

"owner": Represents the name of the account owner.
"movements": Represents an array of numerical values, which are the movement amounts (deposits and withdrawals) in the account.
"interestRate": Represents the interest rate for the account.
"pin": Represents the PIN (Personal Identification Number) associated with the account.
"movementsDates": Represents an array of strings that represent the dates and times of the corresponding movements in the account.
"currency": Represents the currency associated with the account.
"locale": Represents the locale or language for formatting purposes.

The JSON object contains three account objects:
The first account belongs to "Kiara Pajova" and has movement amounts, interest rate, PIN, movement dates, currency (EUR), and locale (pt-PT).
The second account belongs to "Sexhi Picaku" and has similar properties with different values.
The third account belongs to "Stiv Daiu" and has similar properties with different values.
Each account object provides information about the account holder, their transaction movements, interest rate, PIN, movement dates, currency, and locale.



# index.html

`<!DOCTYPE html>:` This declaration specifies the HTML version being used, which is HTML5.
`<html lang="en">:` This opening tag represents the root element of the HTML document and specifies the language of the content (English in this case).
`<head>:` This section contains meta information and external resources used by the HTML document.
`<meta charset="UTF-8">:` Specifies the character encoding of the document as UTF-8, which supports a wide range of characters.
`<meta name="viewport" content="width=device-width, initial-scale=1.0">:` Sets the viewport configuration for responsive design, ensuring the page adapts to different device screen widths.
`<meta http-equiv="X-UA-Compatible" content="ie=edge">:` Specifies the compatibility mode for Internet Explorer.
`<link rel="shortcut icon" type="image/png" href="/icon.png">:` Specifies the favicon (shortcut icon) for the webpage displayed in the browser tab.
`<link href="https://fonts.googleapis.com/css?family=Poppins:400,500,600&display=swap" rel="stylesheet">:` Loads a font stylesheet from Google Fonts API, specifically the Poppins font with various weights.
`<link rel="stylesheet" href="style.css">:` Links an external CSS file named "style.css" to the HTML document.
`<title>Bankist</title>:` Sets the title of the webpage displayed in the browser tab to "Bankist".
`<body>:` This section contains the visible content of the webpage.
`<nav>:` Represents the navigation section of the webpage.
`<p class="welcome">Log in to get started</p>:` Displays a welcome message.
`<img src="logo.png" alt="Logo" class="logo">:` Displays an image logo.
`<form class="login">:` Represents a login form.
`<input type="text" placeholder="user" class="login__input login__input--user">:` Accepts user input for the username.
`<input type="password" placeholder="PIN" maxlength="4" class="login__input login__input--pin">:` Accepts user input for the PIN (masked input with a maximum length of 4 characters).
`<button class="login__btn">&rarr;</button>:` Represents a login button.
`<main class="app">:` Represents the main content of the webpage.
`<div class="balance">:` Displays the account balance.
Various child elements to display the label, date, and value of the balance.
`<div class="movements">:` Displays the account movements (deposits and withdrawals).
Multiple `<div class="movements__row">` elements, each representing a single movement with type, date, and value.
`<div class="summary">:` Displays the summary of account transactions.
`<p>` elements to display labels and values for total In, total Out, and Interest.
`<button class="btn--sort">&downarrow; SORT</button>:` Represents a button for sorting the transactions.
`<div>` elements representing different operations such as money transfer, loan request, and account closure. Each operation has a heading, a form, and input fields/buttons specific to that operation.
`<p class="logout-timer">:` Displays a logout timer message.
`<span class="timer">:` Represents a dynamic timer value that counts down.
`<script src="script.js"></script>:` Links an external
  
  
  
  # script.js
  
  This code represents a banking application called "Bankist". It is responsible for managing user accounts, displaying account information, performing transactions, and providing various banking operations.

Let's go through the code step by step:

"use strict"; enables strict mode in JavaScript, which helps catch common programming mistakes and prevents the use of certain error-prone features.

The code starts by declaring some variables and an array:

account1, account2, and account3 are used to store individual account information.
accounts is an array that will store all the user accounts.
The fetchData function is defined to fetch data from a JSON file called "data.json" using the Fetch API. It retrieves the account information from the JSON file, adds the accounts to the accounts array, and calls the createUsernames function to generate unique usernames for each account.

The code then selects various DOM elements using document.querySelector() and assigns them to corresponding variables. These elements represent different parts of the user interface.

Several helper functions are defined:

`formatMovementDate:` Formats the date of a transaction based on the number of days passed.
`formatCur:` Formats a number as currency based on the locale and currency provided.
`displayMovements:` Displays the account movements (deposits and withdrawals) in the UI.
`calcDisplayBalance:` Calculates and displays the account balance.
`calcDisplaySummary:` Calculates and displays the summary of total income, total outgoing, and interest earned.
`createUsernames:` Generates usernames for each account based on the account owner's name.
The updateUI function is defined to update the user interface with the current account's information. It calls the other helper functions to update the movements, balance, and summary.

The `startLogOutTimer` function sets up a timer that logs out the user after a certain period of inactivity.

Event handlers are added to handle user interactions:

The `btnLogin` click event handler checks the username and PIN entered by the user, authenticates the user, and updates the UI if the login is successful.
The `btnTransfer` click event handler handles money transfer between accounts.
The `btnLoan` click event handler handles loan requests and adds the loan amount to the account.
The `btnClose` click event handler closes the current account if the username and PIN entered are correct.
The `btnSort` click event handler sorts the account movements in ascending or descending order.
Overall, this code sets up the banking application, fetches account data, handles user interactions, and updates the user interface accordingly.
  
  
  
 # style.css
  
  The * selector is used to apply the following styles to all elements on the page: margin and padding set to 0, and box-sizing set to inherit.
The html selector sets the font size to 62.5% (to make it easier to use rem units) and sets box-sizing to border-box.
The body selector styles the body element with a specific font family, color, background color, height, and padding. It also uses the Poppins font and sets a 2rem padding on all sides.
The nav selector styles a navigation element with flexbox properties to display its children in a row, justify the content between them, and align them vertically in the center. It also adds padding on the horizontal sides.
The `.welcome` class styles an element with a font size of 1.9rem and a font weight of 500.
The `.logo` class styles an element with a height of 5.25rem.
The `.login` class styles an element with display set to flex.
The `.login__input` class styles input elements with various properties like border, padding, font size, font family, text alignment, width, border radius, and transition.
The `.login__input:`focus selector styles the input when it is in focus with a different border color.
The `.login__input:`:placeholder selector styles the placeholder text color.
The `.login__btn` class styles button elements with various properties like border, background, font size, color, and cursor. It also has transition effects on hover and focus.
The `.app` class styles a container element with a maximum width, margin, display as a grid, grid template columns and rows, and gap between grid items. It also sets the initial opacity to 0 and adds a transition effect.
The `.balance` class styles an element with display set to flex, aligns items to the flex-end, justifies the content between them, and adds a margin at the bottom.
The `.balance__label`, `.balance__date`, and `.balance__value` classes style specific elements with various font sizes, font weights, and margins.
The `.movements` class styles a container element with a grid row, background color, border radius, and scrollable overflow.
The `.movements__row` class styles rows in the movements container with padding, display as flex, aligns items to the center, and adds a bottom border.
The `.movements__type` and `.movements__date` classes style specific elements with font sizes, text transformations, font weights, and colors.
The `.movements__type--deposit` and `.movements__type--withdrawal` classes add background gradients to specific elements.
The `.movements__value` class styles a specific element with a font size and margin.
The `.summary` class styles a container element with a grid row, display as flex, aligns items to the baseline, padding, and margin.
The `.summary__label` and `.summary__value` classes style specific elements with font sizes, font weights, text transformations, and margins. Some of them also have specific colors.
The `.btn--sort` class styles a specific element with a margin, border, background, font size, font weight, and cursor.
The `.operation` class styles elements with border radius, padding, and color.

  
  
  






