# Test plan

Back to [README](https://github.com/Carina-P/ms3-best-books/blob/master/README.md)

## Contents
- [Tests of functionality and responsiveness](#tests-of-functionality-and-responsiveness)
  * [Test cases](#test-cases)
    + [Test protocol](#test-protocol)
- [UX testing](#ux-testing)
- [Code validation](#code-validation)
  * [Validation with W3S](#validation-with-w3s)
  * [Validation with JSHint](#validation-with-jshint)
  * [Validation with PEP8](#validation-with-pep8)
- [Different browsers](#different-browsers)
- [Some of the bugs](#some-of-the-bugs)
- [Remaining bugs](#remaining-bugs)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>

The below plan for testing was followed during development of the site:
The TDD, **TestDriven Development**, process is followed as much as possible. 
Test cases are developed/thought off, before the code is implemented. The test
process is conducted in an iterative manner and implementation cycles are short
with small code parts every time. In some cases, **prototyping** is used and
the thorough test is done when satisfied with the prototype.

Before new code is committed, testing of all code developed earlier are
repeated again.

When all features are implemented and tested, the following tests are 
performed:
- Go through the test cases for functional testing and testing of
responsiveness, as described below
- **HTML-code validated** by 
[W3S Markup validation service](https://validator.w3.org/)
- **CSS-cod validated** by 
[W3S CSS validation service](https://jigsaw.w3.org/css-validator/)
- **JavaScript-code validated** by [JSHint](https://jshint.com/)
- **Python** code is **validated** by [PEP8](https://pypi.org/project/pep8/) 
- The site is tested on **different browsers**, as described below
- The **deployed version** in heroku is tested

## Tests of functionality and responsiveness
Functionality tests and tests of responsiveness are done by following test cases
below.
Test of responsiveness is mainly performed with help of Chrome Developers Tool. 
The site is also tested with iPad mini and iPhone8.

### Test cases
Test cases are described below and linked to use cases. Each test case have
a name beginning with TC and then a number, for example TC_001.

When testing: Please **start with** testcases **TC_015, TC016, TC017 and TC020**

- Testing use case **US_001**. As a user I want to browse for a book:

    **TC_001** Browse for a book by giving the books title:
    - How to test:
        - Go to homepage and look for the header: "Search for book in this databas" or
        Use navigation bar and choose "Search for book"
        - Print "Where the Crawdads Sing" in the field
        - Press return
    - Expected outcome:
        - View is moved to the "Search results" page.
        - The book is found there. Or message that book is not present in site.
        - Check that information in database corresponds to the result in the page.

    **TC_002** Browse for book by giving an author:
    - How to test:
        - Go to homepage and look for the header: "Search for book in this databas" or
        Use navigation bar and choose "Search for book"
        - Print "August Strindberg" in the field
        - Press return
    - Expected outcome:
        - View is moved to "Search results" page.
        - Book written by August Strindberg is found there. Or message that book is
        not present in site.
        - Check that information in database corresponds to the result in the page.
    **TC_003** Browse for book by giving part of title
    - How to test:
        - Go to homepage and look for the header: "Search for book in this databas" or
        Use navigation bar and choose "Search for book"
        - Print "Crawdads Sing" in the field
        - Press return
    - Expected outcome:
        - View is moved to the "Search results" page.
        - The book is found there. Or message that book/s is not present in site.
        - Check that information in database corresponds to the result in the page.

    **TC_004** Browse for book by giving part of an author's name:
    - How to test:
        - Go to homepage and look for the header: "Search for book in this databas" or
        Use navigation bar and choose "Search for book"
        - Print "August" in the field
        - Press return
    - Expected outcome:
        - View is moved to the "Search results" page.
        - Book/s written by August Strindberg is found there. Or message that book is
        not present in site.
        - Check that information in database corresponds to the result in the page.

- Testing use case **US_002**. As a user I want to see detailed information about a book: 

    **TC_005** See detailed information about a book
    - How to test:
        - Go to homepage and look for the header: "10-top books" or
        Use navigation bar and choose "10-top books"
        - In carousel choose a book and press the button/link: "Book details"
    - Expected outcome:
        - Page "Book details" appears with information about chosen book.
        - Check that information in database corresponds to the result in the page.


- Testing use case **US_003**. As a user I want to buy a book:

    **TC_006** Buy a book
    - How to test:
        - Go to homepage and look for the header: "10-top books" or
        Use navigation bar and choose "10-top books"
        - Choose one book and press buy-link/button in top right corner
    - Expected outcome:
        - Modal with the heading "Thank you" is shown.
        - And also a fake affiliate link appears. In future user is directed to a page 
        where he/she can buy the book.
        - Check that information in database corresponds to the result in the page.


- Testing use case **US_004**. As a user I want to see which books are most popular on the site:

    **TC_007** See the most popular books on the site
    - How to test:
        - Go to homepage and look for the header: "10-top books" or
        Use navigation bar and choose "10-top books"
    - Expected outcome:
        - Moved to carousel that shows a "list" with the sites 10 most popular books,
        including average grade and author for each book.
        - Check that information in database corresponds to the result in the page.


- Testing use case **US_005**, As a user I want to look for book in a category:

    **TC_008** Look for a book in a category
    - How to test:
        - Go to homepage and look for header: "Best in Category" or 
        Go to navigation bar and choose "Best books in category"
        - Press button/link that says "Fiction"
    - Expected outcome:
        - Moved to page that shows search results
        - Books within the category should be shown in the results.
        - Check that information in database corresponds to the result in the page.


- Testing use case **US_006**, As a user I want to add book to the site:

    **TC_009** Add book
    - How to test:
        - Log in, if needed sign in first (see TC015)
        - In navigation bar choose: "Add Book"
        - In "search-field" print: "Pippi Longstocking"
        - Press "Choose" for the book called "Pippi Longstocking goes Aboard" from 2015-09-10 in the search-results
        - Scroll down in "Retrieved information" and:
            - Choose category "Young & Children"
            - Give it the grade 4 in selection list
            - Add a review "This is a very good children's book"
            - Click "Add Book"
    - Expected outcome:
        - Moved to page "Book details" with information about
        the book that now has been added.
        - Also when on homepage searching for "Pippi Longstocking" the book added
        should appear in search list.
        - Look in database. Book with information should appear in both books and book_details and reviews collections.


- Testing use case **US_007**, As a user I want to edit information about a book:

    **TC_010** Edit book information
    **Notice!** This test is **obsolete** since use case is not yet implemented.
    - How to test:
        - Log in with same user as added Pippi Longstocking
        - Search in search-field ("Search for book" in navbar) for "Pippi Longstocking"
        - In search result, find "Pippi Longstocking goes Aboard"
        - Press "Book Details"-button/link
        - In "Book details-page press "Edit book info"
        - Change author to "A Lindgren"
        - Press "Submit/Save"-button
    - Expected outcome:
        - When looking at the book the author is A Lindgren instead of Astrid 
        Lindgren.
        - Check database that author is changed in book collection.


    - Testing use case **US_008**, As a user I want to remove book:

        **TC_011** Remove book
        - How to test:
            - Log in with same user as added Pippi Longstocking
            - Search in search-field (navbar "Search for book") for "Pippi Longstocking"
            - In search result, find "Pippi Longstocking goes Aboard"
            - Press "Book Details"-button/link
            - In "Book details-page press "Delete Book"
        - Expected outcome:
            - A message on top of homepage informing that book is deleted.
            - When searching for the book it no longer appears on the site.
            - Check in database that book has disappearded from books, books_details and if relevant the reviews collections.


- Testing use case **US_009**, As a user I want to grade a book **and* use case
**US_010**, As a user I want to review a book:

    **TC_012**: Grade and review a book
    - How to test:
        - Log in, if needed sign in first (See TC015)
        - In navbar choose "Search for book"
        - In search-form print "Where the crawdads sings"
        - In search results choose book with title "Where the Crawdads Sing" and press
        "Book details"
        - Notice average grade given to the book
        - Press Add opinion
        - In "Opinion"-modal:
            - Choose a grade 5
            - Print review: "The best book I have read"
        - Press "Submit" button
    - Expected outcome:
        - "Book Details" page is shown with the added opinion first.
        - Notice if average grade is changed according to what you expected from
        given a new grade of 5.
    - Check in database that opinion is added to both the book_details and reviews collection.


- Testing use **case US_011**. As a user I want to edit my opinion of a book:

    **TC_013** Edit opinion
    - How to test:
        - Log in with same user as added review and grade for 
        "Where the Crawdads Sing" (TC_012)
        - In Homepage search for "Where the crawdads sings"
        - In search results press "Book Details" for the book
        - In "Book details"-page find the  added opinon in TC012.
        - Press "Change" for this opinion
        - Change grade from 5 to 3.
        - Change review: 
            - Replace "The best book" with "A good book"
        - Press "Submit" button
    - Expected outcome:
        - Redirected to an updated "Book Details" page where
        the opinion is changed.
        - Check the effect on average grade.
        - Check in database that opinion is changed both in book_details and reviews collections.


    Testing use case US_012. As a user I want to remove my opinion of a book:

    **TC_014** Remove opinion
    How to test:
        - Log in with same user as added review and grade for 
        "Where the crawdads sings" (TC_012)
        - In Homepage search for "Where the crawdads sings"
        - In search results press "Book Details" for the book
        - In "Book details"-page find the opinion added in TC012.
        - Press "Delete" for this opinion
    - Expected outcome:
        - User redirected to "Book details" page without the removed opinion.
        - Average grade should be updated.
        - The opinion should be removed from both book_details and reviews collections in database.


-Testing use **case US_0013**. As a user I want to Sign up for the site:

    **TC_015** Sign up to the site
    - How to test
        - If already logged in: Press "Log out" in navbar.
        - In navigation bar choose "Sign Up"
        - In form:
            - Add name: "David"
            - Add password: "Ilovesoccer"
            - Press "Submit"-button
    - Expected outcome
        - Redirected to homepage with A welcome-message in the top.
        - Check in database that the user David is added to users collection.


- Testing use case **US_0014**, As a user I want to log in to the system:

    **TC_016** Log in
    - How to test:
        - If already logged in: Press "Log out" in navbar.
        - In navigation bar choose "Log in"
        - In form:
            - Print name: "David"
            - Print password: "Ilovesoccer"
            - Press "Submit"-button
    - Expected outcome:
        - A welcome text in the top of Homepage


- Testing use case **US_0015**, As a user I want to log out of the system:

    **TC_017** Log out
    - How to test:
        - If not logged in: Log In (see TC016)
        - In navigation bar, choose Log out.
    - Expected outcome:
        - A message that you are logged out in top of the Homepage.
 

- Testing use case **US_0016**. As a "administrative" user I want to add category group:
**Notice**: The administrative authority is not implemented yet. Any user can 
add category groups.
    **TC_018** Add category
    - How to test:
        - In navigation bar choose "Log In"
        - In Log In-page give:
            - Name: test
            - Password: Averydifficultone
        - In navigation bar choose "Manage category groups"
        - In "Manage Category groups"-page press "Add new group"-button
        - In "Add/Edit Category group"-page give:
            - Category name: Horor
            - Press "Submit"-button"
    - Expected outcome:
        - The new category is added to list of category groups in "Category groups"-page
        - In homepage, the new category is shown if "Best books in category" is chosen in
        navigation bar.
        - Check in database that Horor is present in collection category_groups


- Testing use case **US_0017**. As an "administration" user I want to edit and remove categories:
**Notice**: The administrative authority is not implemented yet. Any user can 
edit category groups.
    **TC_019** Edit category
    - How to test:
        - Login as test (See TC_018)
        - In navigation bar choose "Manage category groups"
        - Choose category "Horor" and press the "Edit"-button for this
        category group.
        - In "Edit category"-page category groups name to "Horror"
        - Press "Submit"-button
    - Expected outcome:
        - The category group is changed in the list of category groups in "Category groups"-page
        - In homepage the changed category group is shown, if "Best books in category" is chosen in
        navigation bar.
        - Check in database that collection category_groups is updated.

- Testing **general features**:
    **TC_020** Navbar works as expected
    - How to test:
        - Press each item in navbar one after the other.
        - Press the brand image.
    - Expected outcome:
        - Redirected to expected place after each choice.
        - When pressing the navbar redirection to homepage is expected.

    **TC021** Footer links
    - How to test:
        - Go to bottom of home page.
        - Press each link in footer one at a time.
    - Expected outcome:
        - User is redirected to each social links page.

    **TC22** Carousel with 10 top books works as expected.
    - How to test:
        - Choose "10-top books" in navbar.
        - Just wait a few seconds and see what happens.
        - Press right arrow on right side of carousel.
        - Press left arrow on left side of carousel.
        - Press any of indicators in bottom of carousel.
    - Expected outcome:
        - Carousel should be moving on its own showing the best books in 
        ascending order.
        - When pressing right arrow carousel shows next book.
        - When pressing left arrow carousel shows previous book.
        - When pressing an indicator carousel moves to associated slide.

    **TC023** All buttons/links not tested above:
    - How to text:
        - Check all buttons/links that is not tested above:
            - Buy (Home page/carousel, Book Details page, Search result page)
            - Book Details (Home Page/carousel, Search result page)
            - Add opinion (Home page/carousel, Book details page, Search result page ),
            - Choose category group for best books (Home page/Best in category)
            - This database( Home page/search book in this database)
            - Search Books (Home page/add book)
            - Choose Book (Home page/add book/search results)
            - Add Book ( Home page/add book/search results/retrieved information about the book)
            - Cancel ( Home page/add book/search results/retrieved information about the book and
            Add category group page)
            - "Close-image" in top right corner (Book details page and Search results page)
    - Expected outcome:
        - Check that you end up where you expected. Moreover, if it is a Cancel button that nothing is
        changed on pages or in database.

#### Test protocol
The outcome of testing according to above test cases is documented in [Test Protocol](https://github.com/Carina-P/ms3-best-books/blob/master/test/protocol_test_cases.pdf).


## UX testing
UX testing is **conducted by watching and interviewing users** when they used
the page. Examples of issues/discussions:
- I had the **"brand-image" in the middle of the navbar** from the beginning. However users
wanted it to the **left instead**. Had a discussion with them if I should have a navitem
called home also/instead of bar image. They thought it was well known that 
brand-image is the way to the home page.
- I had **this picture on all pages above navbar**:

![Image above navbar](https://github.com/Carina-P/ms3-best-books/blob/master/static/images/bookshelf.jpg?raw=true)
Users thought it was **too much** with this picture and a "start-picture" on the 
home page. So I **removed it from home, login and sign up pages**.
- In Add book-form I have the background color: **acid green**, in the part of the
form **user has to fill in**. (The rest of the form is information fetched from Google
Books that is not supposed to be changed.):

![Part in add book form for user to fill out](https://github.com/Carina-P/ms3-best-books/blob/master/wireframes/retrieved_information_to_add_book_2.jpg?raw=true)
The green part **was in the beginning of the form**. I thought this was a way to **get
users attention** quickly to this part of the form. 
User thought it was **good that the background is green** but they thought it was 
**confusing** that it was in the **beginning** of the form.
**Solution**: I **moved** the green part **to bottom of form**.
- Users wanted a **Close-button** in "Book Details page" and "Search result page":
![Close-button](https://github.com/Carina-P/ms3-best-books/blob/master/wireframes/close.jpg?raw=true)
- I started with using **Materialize** but after a while, I **felt limited** compared to Bootstrap, especially when 
trying to do a carousel and also for card decks. Therefore, I did a big **change to Bootstrap**.


## Code validation
### Validation with W3S
- **HTML**: Validated with **no errors** or warnings. Notice! Some headers are filled from JavaScript, if
code is validated when the JavaScript has not been run, you will get warnings about empty headers. That 
applies to code belonging to Add Book and also for Modals.
    - In GitHub the template: form_add_book.html, is marked as it has an error. The code is working as
    I want it to and I cannot find any problem. I talked to Code Institutes Tutore, and they told me
    "The code is fine but validators don't want to read JavaScript functionality on a HTML page in the body content."
- **CSS**: Validated with **no errors** or warnings.

### Validation with JSHint
**JavaScript** validated with **no errors**. 
- There are **one undefined variables**: 
    - $ (JQuery)
- There are **seven unused variables**:
    - moveTo, cancelAddBook, addBook, searchBooks, addOpinion, changeOpinion and buyBook:
    These are all functions called from HTML.

### Validation with PEP8
PEP8 was included in the IDE and thus the **python** code is validated within GitHub.
Validation without errors or warnings.

## Different browsers
The code is **mainly tested with Chrome**. But also **Firefox and Safari**.
- According to [W3 Schools](https://www.w3schools.com/js/js_es6.asp) the 
**JavaScript** code will probably not work well on browsers less than the 
following versions: **Chrome 58, Edge 14, Firefox 54, Safari 10 and Opera 55**. 
That are because following features from **ECMAScriptS6** is used: 
    - let
    - template literal syntax
    - arrow function
- **Bootstrap 4** is used and according to [Bootstrap](https://getbootstrap.com/docs/4.6/getting-started/browsers-devices/)
you need at least: 
**Chrome 45, Firefox 38, Edge 12, IE10, iOS 9, Safari 9, Android 4.4 and Opera 30**.
- **HTML5 semantics and form features** are used, according to [Can I use](https://caniuse.com/?search=HTML5), that requires at least:
**IE9, Firefox 4, Safari 4 and Android Browser 4.4**. **Opera mini** cannot be used.
    

## Some of the bugs
- Got a warning in console that **links to book cover images** were **not secure**. The link is retrieved from Google Books and they have links 
to http instead of https. **Solution** replace "http/" in the string with "/https".
- **Average grade** for a book must be **recalculated** if user **changes or deletes** an opinion.
- On smaller devices navbar has a "hamburger menu". When user clicks on the "hamburger": menu alternatives 
are shown. If user then clicks on a menu alternatives: the user is directed to chosen place in the site, and menu 
is "closed/hidden". However **when the menu is "closed"**: The **marker ends up further down in page** than expected.
**Solution**: Found JS code on [Stackoverflow](https://stackoverflow.com/questions/4086107/fixed-page-header-overlaps-in-page-anchors) 
by [Adrian Garner](https://stackoverflow.com/users/573373/adrian-garner) that I modified to scroll to offset top and problem was solved.
- Same modal is used for Add opinion and Change opinion. In the beginning I had modal for adding opinion
as "standard" in the HTML-code. When user wanted to change opinion, values were put into the modal from JavaScript.
I realized that if user **leaves modal without submitting** (that is by close-button), the modal is not
cleared and when user wants to add another opinion, **values from earlier (wrong values) are shown in the modal**.
**Solution**: **JavaScript** is called **both for add opinion and change opinion to control what is present in modal**.
- The search for books, in home page, giving title or author or part of title or authors name, was **case sensitive**.
Some titles mix lowercase and uppercase letters and makes them **hard to find, if case sensitive**.
**Solution**: Using **text index** on collection books which also improves performance.
- By using the **"Back button"** user could return to login page or sign up page after having logged in. 
User was also able to manage category pages after being logged out. This is not supposed to happen.
**Solution**: In the python view, test if user is logged in alternatively not, in above case.
 


## Remaining bugs
- I guess the following is **not a bug**, but it got me really confused: If I use **"inspect" in Chomes Developers Tool**
when looking at Best Books, suddenly/randomly? the **select-lists** in "opinion"-modal stops
working. However if I remove the "inspect"-"mode" everything works OK again.
- Warning from Lighthouse in Chomes Dev Tool: **Contrast in brand-image in navbar is not enough**. I have chosen to not fix this.