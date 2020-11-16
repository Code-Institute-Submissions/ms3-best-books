# Test plan

Back to [README](https://github.com/Carina-P/ms3-best-books/blob/master/README.md)

The bellow plan for testing was followed during development of the site:
The TDD, **TestDriven Development**, process is followed. Test cases is
developed/thought off, before code is implemented. The test process is
conducted in an iterativ manner and implementation cycles are short with
small code parts every time. 

Before new code is commited, testing of all code developed earlier are
tested again.

When all features are implemented and tested the following tests are 
performed:
- Go through the test cases for functional testing and testing of
responsiveness, as described below
- **HTML-code validated** by 
[W3S Markup validation service](https://validator.w3.org/)
- **CSS-cod validated** by 
[W3S CSS validation service](https://jigsaw.w3.org/css-validator/)
- **JavaScript-code validated** by [JSHint](https://jshint.com/)
- The site is tested on different browsers, as described below
- The deployed version is tested

<!-- Manual testing only or automated tests also? - description of each!! -->

## Tests of functionality and responsiveness
Functionality tests and tests of responsiveness is done by following test cases
below.
Test of responsiveness is mainly performed with help of Chrome Developers Tool. 
But the site is also tested with iPad mini and iPhone8.

### Test cases

Testing use case US_001, As a user I want to browse for a book:

**TC_001** Browse for a book by giving the books title:
- How to test:
    - Go to field for searching.
    - Print "Where the crawdads sings" in the field
    - Press return
- Expected outcome:
    - View is moved to the page's "Search results" part.
    - The book is found there. Or message that book is not present in site.

**TC_002** Browse for book by giving an author:
- How to test:
    - Go to field for searching.
    - Print "August Strindberg" in the field
    - Press return
- Expected outcome:
    - View is moved to the page's "Search results" part.
    - Book written by August Strindberg is found there. Or message that book is
    not present in site.

**TC_003** Browse for book by giving part of title
- How to test:
    - Go to field for searching.
    - Print "crawdads sings" in the field
    - Press return
- Expected outcome:
    - View is moved to the page's "Search results" part.
    - The book is found there. Or message that book/s is not present in site.

**TC_004** Browse for book by giving part of an authors name:
- How to test:
    - Go to field for searching.
    - Print "August" in the field
    - Press return
- Expected outcome:
    - View is moved to the page's "Search results" part.
    - Book/S written by August Strindberg is found there. Or message that book is
    not present in site.


Testing use case US_002, As a user I want to see detailed information about a book: 

**TC_005** See detailed information about a book
- How to test:
    - Go to list of most popular books
    - Choose one of the books and press details link/button.
- Expected outcome:
    - Page "About book" appears with information about choosen book.


Testing use case US_003, As a user I want to buy a book:

**TC_006** Buy a book
- How to test:
    - Go to list of most popular books
    - Choose one book and press buy-link/button
- Expected outcome:
    - Linked to a page with possibility to buy the choosen book


Testing use case US_004, As a user I want to see which books are most popular on the site:

**TC_007** See the most popular books on the site
- How to test:
    - Go to homepage and look for the header: "Most popular books" or
    - Use navigation bar and choose "Popular"
- Expected outcome:
    - Moved to view that shows a list with the sites most popular books,
    including average grade for each book.


Testing use case US_005, As a user I want to look for book in a category:

**TC_008** Look for a book in a category
- How to test:
    - Go to navigation bar and choose "Categories"
    - Press button/link that says "Mystery and Thriller"
- Expected outcome:
    - Moved to view that shows search results
    - Books within the category should be shown in the results.


Testing use case US_006, As a user I want to add book to the site:

**TC_009** Add book
- How to test:
    - Log in, if needed sign in first
    - In navigation bar choose: "Add Book"
    - In "search-field" print: "Pippi Longstocking"
    - Press "Add book to this site" for the book from 2020 in the search-results
- Expected outcome:
    - Moved to page "Book details/Manage Book" with information about
    the book that now has been added.
    - Also when on homepage searching for "Pippi Longstocking" the book added
    should appear in search list


Testing use case US_007, As a user I want to edit information about a book:

**TC_010** Edit book information
- How to test:
    - Log in with same user as added Pippi Longstocking
    - Search in search-field for "Pippi Longstocking"
    - In search result, find "Pippi Longstocking"
    - Press "Book Details"-button/link
    - In "Book details/Manage Book"-page press "Edit book info"
    - Change author to "A Lindgren"
    - Press "Submit/Save"-button
- Expected outcome:
    - When looking at the book the author is A Lindgren instead of Astrid 
    Lindgren.


Testing use case US_008, As a user I want to remove book:

**TC_011** Remove book
- How to test:
    - Log in with same user as added Pippi Longstocking
    - Search in search-field for "Pippi Longstocking"
    - In search result, find "Pippi Longstocking"
    - Press "Book Details"-button/link
    - In "Book details/Manage Book"-page press "Edit book info"
    - Change author to "A Lindgren"
    - Press "Submit/Save"-button
- Expected outcome:
    - When searching for the book it no longer appears on the site.


Testing use case US_009, As a user I want to grade a book **and* use case
US_010, As a user I want to review a book:

**TC_012**: Grade and review a book
- How to test:
    - Log in, if needed sign in first
    - On homepage search for "Where the crawdads sings"
    - In search results choose book with title "Where the crawdads sings"
    - Notice average grade given to the book
    - Press Add opinion
    - In "Manage opinion"-modal:
        - Choose a grade 5
        - Print review: "The best book I have read"
    - Press "Submit/Save" button

- Expected outcome:
    - In Homepage search for "Where the crawdads sings"
    - Look in search result for the book and notice if the average grade
    has changed according to the grade given.
    - Press "Book Details"
    - The added review should appear in reviews list in "Book Details"-page


Testing use case US_011, As a user I want to edit my opinion of a book:

**TC_013** Edit opinion
- How to test:
    - Log in with same user as added review and grade for 
    "Where the crawdads sings" (TC_012)
    - In Homepage search for "Where the crawdads sings"
    - In search results press "Book Details" for the book
    - In "Book details/Manage book"-page find the review added in TC012.
    - Press "Edit review" for this review
    - Change grade from 5 to 4.
    - Change review: 
        - Replace "The best book" with "Among the 10 best books"
    - Press "Submit/Save" button
- Expected outcome:
    - In Homepage search for "Where the crawdads sings"
    - Look in search result for the book and notice if the average grade
    has changed according to the grade given.
    - Press "Book Details"
    - Look for review and notice if changed.


Testing use case US_012, As a user I want to remove my opinion of a book:

**TC_014** Remove opinion
How to test:
    - Log in with same user as added review and grade for 
    "Where the crawdads sings" (TC_012)
    - In Homepage search for "Where the crawdads sings"
    - In search results press "Book Details" for the book
    - In "Book details/Manage book"-page find the review added in TC012.
    - Press "Remove review" for this review
    - Press Yes when question "Are you sure?" appears
- Expected outcome:
    - In Homepage search for "Where the crawdads sings"
    - Look in search result for the book
    - Press "Book Details"
    - Removed review should not appear


Testing use case US_0013, As a user I want to Sign up for the site:

**TC_015** Sign up to the site
- How to test
    - In navigation bar choose "Sign Up"
    - In form:
        - Add name: "David"
        - Add email: "david@gmail.com"
        - Add password: "Ilovesoccer"
        - Press "Submit"-button
- Expected outcome
    - A welcome text and a possibility to log in to page.


Testing use case US_0014, As a user I want to log in to the system:

**TC_016** Log in
- How to test:
    - In navigation bar choose "Log in"
    - In form:
        - Print name: "David"
        - Print password: "Ilovesoccer"
        - Press "Submit"-button
- Expected outcome:
    - A welcome text in the Homepage


Testing use case US_0015, As a user I want to log out of the system:

**TC_017** Log out
- How to test:
    - In navigation bar choose Log out.
    - Answere YES to the question: "Are you sure you want to log out?"
- Expected outcome:
    - A message that you are logged out in the Homepage.
 

Testing use case US_0016, As a "administrative" user I want to add categories:

**TC_018** Add category
- How to test:
    - In navigation bar choose "Log In"
    - In Log In-page give:
        - Name: Admin 
        - Password: Averydifficultone
    - In navigation bar choose "Manage categories"
    - In "Manage Categories"-page press "Add Category"-button
    - In "Add/Edit Category"-page give:
        - Category name: Historical Fiction
        - Short Description: Fictional books where the author is inspired by
        an event/person from history.
        -   Colour background: #000000
        -   Colour text: #ffffff
        - Press "Submit"-button"
- Expected outcome:
    - The new category is added to list of categories in "Manage Categories"-page
    - In homepage the new category is shown if "Categories" is choosen in
    navigation bar. And background colour is black and text white.


Testing use case US_0017, As a "administration" user I want to edit and remove categories:

**TC_019** Edit category
- How to test:
    - Login as Admin (See TC_018)
    - In navigation bar choose "Manage categories"
    - Choose category "Historical Fiction" and press the "Edit"-button for this
    category.
    - In "Edit category"-page change colour background to #d00000
    - Press "Submit"-button
- Expected outcome:
    - - The background colour for category is changed
    - In homepage the new category is shown if "Categories" is choosen in
    navigation bar. And background colour is **red** and text white.

#### Test protocol
## UX testing
UX testing is conducted by watching and interviewing users when they used
the page. Examples of issues/discussions:

## Code validation
## Different browsers

## Some of the bugs

## Remaining bugs