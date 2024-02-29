# Mini_Project_Todo_List_App


Software Documentation for ToDo App
This document provides a detailed explanation of the provided HTML, CSS, and JavaScript code for a ToDo App.

1. Functionality Overview:

The code implements a basic ToDo application with the following functionalities:

Adding Tasks: Users can add new tasks by entering them in the input field and clicking the "Add" button.
Deleting Tasks: Users can delete individual tasks by clicking the trash can icon next to each task.
Task Listing: The app displays a list of all currently added tasks.
Task Search: Users can search for specific tasks by entering keywords in the search bar. This filters the displayed tasks based on the search term.
Clear All Tasks: Users can clear all listed tasks at once by clicking the "Clear All" button.
Task Count Display: The app displays the total number of pending tasks at the bottom of the app.
2. Code Breakdown:

HTML Structure (index.html):
Defines the basic structure of the web page using HTML elements.
Includes sections for the heading, search box, task list, and message area.
Links the external CSS file (style.css) and JavaScript file (script.js).
CSS Styling (style.css):
Defines the visual appearance of the app by styling various elements like font size, colors, margins, and paddings.
JavaScript Functionality (script.js):
Contains event listeners that capture user interactions and trigger corresponding functionalities.
Utilizes functions to:
Update the displayed task count (updateMessage).
Add new tasks to the list (addForm.addEventListener).
Delete tasks from the list (tasks.addEventListener).
Clear all tasks (clearAll.addEventListener).
Filter tasks based on search term (filterTask).
Reset the search bar (searchForm.addEventListener).
3. Detailed Code Explanation:

3.1 Adding Tasks:

The addForm variable selects the form element with the class "add".
When the form is submitted (addForm.addEventListener("submit")), the default behavior is prevented (event.preventDefault()).
The value entered in the input field is retrieved and trimmed to remove leading/trailing whitespaces (const value = addForm.task.value.trim()).
If the entered value is not empty (if (value.length)):
A new list item (<li>) is created with the entered task text and a delete icon (innerHTML += ...).
The form is reset (addForm.reset()) to clear the input field.
The task count is updated (updateMessage()).
3.2 Deleting Tasks:

The tasks variable selects the unordered list element with the class "tasks" containing the task list items.
When the user clicks anywhere within the task list (tasks.addEventListener("click")):
If the clicked element has the class "delete" (if (event.target.classList.contains("delete"))):
The entire list item containing the clicked delete icon is removed from the list (event.target.parentElement.remove()).
The task count is updated (updateMessage()).
3.3 Task Search:

The searchForm variable selects the form element with the class "search".
When the user types in the search bar (searchForm.addEventListener("keyup")):
The entered search term is retrieved and trimmed (const term = searchForm.task.value.trim()).
The filterTask function is called with the search term to filter the displayed tasks.
When the user clicks the reset icon in the search bar (searchForm.addEventListener("click")):
The search form is reset (searchForm.reset()).
The filtering function is called with an empty search term to display all tasks.
3.4 Filtering Tasks (filterTask function):

Iterates through all list items using Array.from(tasks.children).
Filters the list items based on whether the task text (converted to lowercase) includes the search term (also converted to lowercase).
Adds the class "hide" to task list items that don't match the search term, effectively hiding them.
Removes the "hide" class from task list items that match the search term, making them visible.
4. Additional Notes:

The code utilizes external libraries for font icons (Bootstrap Icons) and custom fonts (Google Fonts).
Error handling and validation for user input are not implemented in this basic version.
This documentation provides a comprehensive explanation of the code, enabling users to understand the app's
