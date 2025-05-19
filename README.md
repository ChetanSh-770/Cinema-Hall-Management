# Cinema Hall Management System

This is a Python-based system for managing cinema hall operations, including show listings, seat availability, and ticket booking.

# Features

* Show Management: Add and view movie shows with details like movie ID, name, and showtime.
* Seat Availability: Check available seats for a specific show.
* Ticket Booking: Book tickets for customers, select seats, and generate booking details.
* Multiple Halls: Manage multiple cinema halls with different seating configurations.

# Code Description

The code consists of three classes:

* Star_cinema: A base class to manage multiple cinema halls. It contains a list of halls.
* Hall: Represents a cinema hall with attributes like hall name, rows, and columns. It inherits from Star_cinema and provides methods to:
    * Add shows (entry_show)
    * View show list (view_show_list)
    * Show available seats (show_avalible_seats)
    * Book tickets (book_tickets)
* Helper function decoration(): Prints a line separator for better output formatting.

## How to Use

1.  Initialization:
    * Create an instance of `Star_cinema`.
    * Create instances of `Hall` for each cinema hall, providing the hall name, number of rows, and columns.
    * Add shows to each hall using the `entry_show` method.

2.  Main Loop:
    * The program enters a loop that presents a menu with the following options:
        * Show available shows.
        * Show available seats for a selected show.
        * Book tickets.
    * The user selects an option, and the corresponding action is performed.

# Class Details

# `Star_cinema`

* `hall_list`: A class-level list to store `Hall` objects.
* `__init__(self)`: Initializes the `Star_cinema` object.
* `entry_hall(self, hall)`: Adds a `Hall` object to the `hall_list`.

### `Hall(Star_cinema)`

* `_seats`: A dictionary to store the seating arrangement for each show.  The keys are movie IDs, and the values are 2D lists representing the seats. 'X' denotes a booked seat.
* `_show_list`: A list of tuples, where each tuple contains `(movie_id, movie_name, show_time)`.
* `hall_no`: The name or ID of the hall.
* `rows`: Number of rows in the hall.
* `cols`: Number of columns in the hall.
* `customer`: A dictionary to store customer details. (Currently not used, but likely intended for storing customer info with bookings).
* `__init__(self, hall_name, rows, cols)`: Initializes a `Hall` object with the given details, and calls the `Star_cinema` constructor and adds the hall to the list of halls.
* `entry_show(self, movie_id, movie_name, show_time)`: Adds a show to the hall's show list and initializes the seating arrangement for that show.
* `view_show_list(self)`: Prints the list of shows in the hall.
* `show_available_seats(self, movie_id)`: Displays the seating arrangement for a given movie ID.  'X' indicates booked seats, and the row and column are shown for available seats (e.g., A0, B3).
* `book_tickets(self)`: Allows the user to book tickets for a show.  It prompts for movie ID, customer name, phone number, and the number of tickets.  It then prompts for seat numbers, marks the seats as booked ('X'), and displays the booking details.


Improvements
Error Handling: More robust error handling could be implemented (e.g., using try-except blocks) to handle invalid inputs, such as non-integer input for the number of tickets.

Data Persistence: Currently, the data is lost when the program ends.  Consider adding functionality to save and load data from a file or database.

Input Validation: Add validation for seat numbers (e.g., check if they are within the valid range of rows and columns).

Customer Class: Creating a Customer class to store customer information would improve the structure and organization of the code.

Seat Selection Display: Improve the display of seat selection to make it more user-friendly (e.g., show a visual representation of the seating arrangement).

Modularization: For a larger system, consider breaking down the code into multiple modules for better organization and maintainability.

User Interface: A command-line interface is functional, but a graphical user interface (GUI) would significantly enhance the user experience.

Payment Integration: For a real-world application, you would need to integrate a payment gateway to handle ticket payments.

Concurrency: If you want multiple users to be able to book tickets at the same time, you'll need to add concurrency control (e.g., using locks or transactions) to prevent race conditions.
