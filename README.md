# Best Books

This is the site where you get inspired and find new books to read. 
A place with short descriptions of different books and also reviews with other
readers best tips.

The live project can be found here: [https://ms3-best-books.herokuapp.com/](https://ms3-best-books.herokuapp.com/)

## UX
### Strategy Plane
#### Site owner's goal
Get inspired from users reviews and recommendations.
Earn money on each book purchased via link from the site.

#### External users goal
Find books they would like to read.

There are three types of users:
- Those who just want to get inspiration and find books to read: **Viewer**.
- Those who also want to add books to the site and share their thoughts
 about a book/books: **Reviewer**.
- The administrator of the page who manages book categories: **Administrator**.

**Site owners need**
- That it is easy for user to buy book: priority 1.

**Viewers and Reviewers** needs:
- Easy and intuitive way to browse books: priority 1.
- Easy find more information about a book: priority 2.
- Buy book/s. 
- See what other users think about book: priority 2.

**Reviewers** needs:
- Easy search for a book and add book that is not present on site: priority 2.
- Easy grade and give review of book: priority 2.
- Update and remove "own books" (books that user has added) :  priority 3.
- Update and remove "own reviews" (reviews that user has added): priority 3.

**Administrators** needs:
- Authority to edit and remove all ideas of all users: priority 3.
- Authority to manage categories: priority 3.

### Scoope Plane
#### User stories
US_001: As a user I want to browse for a book.
US_002: As a user I want to see detailed information about a book. 
US_003: As a user I want to buy a book
US_004: As a user I want to see which books are most popular on the site.
US_005: As a user I want to look for book in a category.
US_006: As a user I want to add book to the site.
US_007: As a user I want to edit information about the book.
US_007: As a user I want to remove book.
US_008: As a user I want to grade a book.
US_009: As a user I want to review a book.
US_010: As a user I want to edit my opinion of a book.
US_011: As a user I want to remove my opinion of a book.
US_0012: As a user I want to register to the system.
US_0013: As a user I want to log in to the system.
US_0014: As a user I want to log out of the system.
US_0015: As a "administration" user I want to add categories.
US_0016: As a "administration" user I want to edit and remove categories.

#### Features
- Search for books. 
- Search for books belonging to category.
- Easy to buy a book with a link.
- Overview: many books with limited information for each book.
- Possibility to easily get more detailed information about a book.
- Add, edit and remove a book.
- When adding a book: help to fill in information.
- Add, edit and remove review and grade for a book.
- Authentications system: User can only edit and remove "own books" and 
"own reviews".
- Add, edit and remove categories. Authentication system limits this
capability to those with administator privleges.

### Structure Plane

### Skeleton Plane
#### Wireframes

##### Major changes compared to wireframes

### Design Choices
#### Fonts
#### Colours


Use this section to provide insight into your UX process, focusing on who this website is for, what it is that they want to achieve and how your project is the best way to help them achieve these things.

In particular, as part of this section we recommend that you provide a list of User Stories, with the following general structure:
- As a user type, I want to perform an action, so that I can achieve a goal.

This section is also where you would share links to any wireframes, mockups, diagrams etc. that you created as part of the design process. These files should themselves either be included as a pdf file in the project itself (in an separate directory), or just hosted elsewhere online and can be in any format that is viewable inside the browser.

## Features

In this section, you should go over the different parts of your project, and describe each in a sentence or so.
 
### Existing Features
- Feature 1 - allows users X to achieve Y, by having them fill out Z
- ...

For some/all of your features, you may choose to reference the specific project files that implement them, although this is entirely optional.

In addition, you may also use this section to discuss plans for additional features to be implemented in the future:

### Features Left to Implement
- Another feature idea

## Data structure

## Technologies Used

In this section, you should mention all of the languages, frameworks, libraries, and any other tools that you have used to construct this project. For each, provide its name, a link to its official site and a short sentence of why it was used.

- [JQuery](https://jquery.com)
    - The project uses **JQuery** to simplify DOM manipulation.


## Testing

In this section, you need to convince the assessor that you have conducted enough testing to legitimately believe that the site works well. Essentially, in this part you will want to go over all of your user stories from the UX section and ensure that they all work as intended, with the project providing an easy and straightforward way for the users to achieve their goals.

Whenever it is feasible, prefer to automate your tests, and if you've done so, provide a brief explanation of your approach, link to the test file(s) and explain how to run them.

For any scenarios that have not been automated, test the user stories manually and provide as much detail as is relevant. A particularly useful form for describing your testing process is via scenarios, such as:

1. Contact form:
    1. Go to the "Contact Us" page
    2. Try to submit the empty form and verify that an error message about the required fields appears
    3. Try to submit the form with an invalid email address and verify that a relevant error message appears
    4. Try to submit the form with all inputs valid and verify that a success message appears.

In addition, you should mention in this section how your project looks and works on different browsers and screen sizes.

You should also mention in this section any interesting bugs or problems you discovered during your testing, even if you haven't addressed them yet.

If this section grows too long, you may want to split it off into a separate file and link to it from here.

## Deployment

This section should describe the process you went through to deploy the project to a hosting platform (e.g. GitHub Pages or Heroku).

In particular, you should provide all details of the differences between the deployed version and the development version, if any, including:
- Different values for environment variables (Heroku Config Vars)?
- Different configuration files?
- Separate git branch?

In addition, if it is not obvious, you should also describe how to run your code locally.


## Credits

### Content
- The text for section Y was copied from the [Wikipedia article Z](https://en.wikipedia.org/wiki/Z)

### Media
- The photos used in this site were obtained from ...

### Acknowledgements

- I received inspiration for this project from X