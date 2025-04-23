# Vending_machine
Overview

This Shiny app simulates a vending machine interface built using R and the Shiny framework. Users can select an item by its code, insert money, and purchase the item. The app displays the current inventory, checks for sufficient funds and stock availability, and provides feedback on the transaction, including any change returned. The app uses the dplyr, shiny, and tibble packages for data manipulation and interactive web application development.

Features
Item Selection: Choose from a predefined list of items (Chips, Soda, Candy, Water) using their codes (A1, A2, A3, A4).

Money Input: Insert money in increments of $0.25 to purchase an item.

Inventory Management: Tracks stock levels and updates them after each purchase.

Feedback System: Displays messages for successful purchases, insufficient funds, out-of-stock items, or invalid selections.

Real-Time Inventory Display: Shows the current stock and details of available items.

Prerequisites
To run this Shiny app, you need the following:

R: Version 4.0.0 or higher (download from CRAN).

RStudio: Recommended for a user-friendly development environment (download from RStudio).
Required R packages:
dplyr: For data manipulation.
shiny: For building the interactive web application.
tibble: For modern data frame structures.


Installation
Install R and RStudio:
Follow the instructions on the CRAN website to install R.
Download and install RStudio from RStudio.
Install Required Packages: Open R or RStudio and run the following commands to install the necessary packages:

install.packages("dplyr")
install.packages("shiny")
install.packages("tibble")



Save the Code:
Copy the provided R code into a file named app.R (or any preferred name with a .R extension).
Save the file in your working directory.
Usage

Open the Code:
Open app.R in RStudio or your preferred R environment.

Run the App:
Source the entire script or run the final line:
shinyApp(ui = ui, server = server)
This will launch the Shiny app in your default web browser or RStudio's viewer.

Interact with the App:
Select an Item: Use the dropdown menu to choose an item by its code (e.g., A1 for Chips).
Insert Money: Enter the amount of money in the numeric input field (e.g., 1.50 for $1.50).
Purchase: Click the "Purchase" button to attempt the transaction.
View Feedback: Check the message output for transaction status (e.g., "Dispensing Chips. Change returned: $0.00").
Monitor Inventory: The table in the main panel updates to reflect the current stock.
Code Structure

Inventory Definition:
A tibble named vending_machine stores the initial inventory with columns for code, item, price, and stock.
UI:
Built using fluidPage with a sidebar for input controls (item selection, money input, purchase button) and a main panel for the inventory table.

Server Logic:
Uses a reactiveVal to manage the inventory dynamically.
Handles purchase events with validation for stock, funds, and item selection.
Updates the inventory and provides feedback via text output.

Dependencies:
dplyr for filtering and manipulating the inventory data.
shiny for the interactive web interface.
tibble for efficient data frame handling.
Example
Upon running the app, the interface displays:
A dropdown with item codes (A1, A2, A3, A4).
A numeric input for money (e.g., enter 1.50).
A "Purchase" button to initiate the transaction.
A table showing the inventory (e.g., Chips, $1.50, 10 in stock).
A message area for feedback (e.g., "Dispensing Soda. Change returned: $0.50" if $1.50 was inserted for a $1.00 item).

Limitations
The app assumes valid numeric inputs for money (no negative values or non-numeric inputs are validated).
No persistent storage; the inventory resets when the app is restarted.
Limited to four items; expanding the inventory requires manual updates to the vending_machine tibble.
![Screenshot 2025-04-23 112833](https://github.com/user-attachments/assets/1e686078-40f2-43a7-8393-88e6fe1acc85)

Future Improvements
Add input validation for money (e.g., reject negative or non-numeric values).

Implement persistent storage (e.g., save inventory to a CSV file or database).

Expand the item list dynamically via a configuration file.
Add user authentication for administrative tasks (e.g., restocking).
Enhance the UI with visualizations (e.g., stock level charts).
