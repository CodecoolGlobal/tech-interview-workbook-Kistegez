# Web with Python questions

## Software design

### Clean code

#### Point out 5 suggestions, how to format an SQL query!

    - Naming object: Avoid naming in plural, also using capital letters,
        and if it is more than one word use underscore (or CamelCase)
    - Alignment: recommened to writing the first keywords on a new line to the left
        and then the rest of the code to the right.
        If there is many word after select, it is is better to separete them by placing each on a separate line.
    - Keep capitalization consistent: If you do a query capitalized then keep that rule to the otehres
    - Protect your SQL from injection: to insert variables do not use 'f' string. Use sql.SQL() or execute(,dict) instead.
    - Use statements, operators, variables properly
    - Commas are at the end of the line

#### What layers can you name in a simple web application?

    - Presentation layer ("frontend". display UI, goal: input, request send to service)
    - Data service layer ("controller". It is between Business logic layer and Presentation)
    - Business logic layer ("Service". Main logic)
    - Data access layer ("DAO". It access data from database)

### Error handling

#### What error can occur, when an array does not have an element on the requested index?

    An IndexError

#### What is the “finally” block, and how would you use it?

    It is inside a try block and it is executed even if an unexpected exception (catch) occurs.
    It is useful because it allows the programmer to avoid having cleanup code accidentally bypassed.

#### Why should we catch special exception types?
    
    In that way we can see exactly what went wrong.

### Security

#### What is SQL injection? How to protect an application against it?

    When an user doesn't use the INPUT FIELDS properly and writes SQL commands instead, which can break our database or steal sensitive data.
    A code can be protected by writing sql queries in secure way. Each framework has their own solution for that problem.

#### What is XSS? How to protect an application against it?
        
    Cross-site Scripting (XSS) is a client-side (JavaScript) code injection attack.
    The attacker aims to execute malicious scripts in a web browser (of the victim).
    Commonly used for attacks: forums, message boards, comments.
    To protect against stored XSS attacks:
    - DOMPurify
    - make sure any dynamic content coming from the data store cannot be used to inject JavaScript on a page.
    - Whitelist Values HTTP-only Cookies : meaning that cookies will be received, stored, and sent by the browser, but cannot be modified or read by JavaScript.
    - Disallow characters – especially < and > characters – from being rendered.

#### How to properly store passwords?

    You have to hash them (salting them is also recommended) and then store the outcome in a database.

#### What is HTTPS?

    HyperText Transfer Protocol Secure (HTTPS) is an extension of the Hypertext Transfer Protocol (HTTP).
    It is used for SECURE COMMUNICATION OVER COMPUTER NETWORK, and is widely used on the Internet.
    It protects against man-in-the-middle attacks!!

#### What is encryption and decryption?

    HTTPS does that.
    - Encryption: The process of translating plain text data (plaintext) into something that appears to be random and meaningless (ciphertext).
    - Decryption: The process of converting ciphertext back to plaintext.

#### What is hashing?
    
    A hash function is where a computer takes an input of any length and content (e.g. letters, numbers, and symbols) and
    uses a mathematical formula to chop it, mix it up, and produce an output of a specific length.
    
#### What is the difference between encryption and hashing? When would you use which?
    
    The key difference between encryption and hashing is that encrypted strings can be reversed back into their original decrypted form if you have the right key.
    - Hashing: Ideal way to store passwords, as hashes are inherently one-way in their nature.(+ salt)
    - Encryption: Ideal for sending secure messages.

#### What encryption methods do you know?

    Symetric encryption: uses one key and it is shared with everyone who use it. FASTER BUT LESS SECURE
    Asymetric encrytion: public key is shared with everyone for encryption and public key is owned who has to decrypt it. MOST SECURE
    
    AES (Advanced Encryption Standard): It is symetric encryption algorithm that encrypts fixed blocks of data (of 128 bits) at a time.
    The keys used to decipher the text can be 128-, 192-, or 256-bit long. The 256-bit key encrypts the data in 14 rounds, the 192-bit key in 12 rounds, and the 128-bit key in 10 rounds.

    RSA (Rivest-Shamir-Adleman): It is an asymmetric encryption algorithm that is based on the factorization of the product of two large prime numbers.
    Only someone with the knowledge of these numbers will be able to decode the message successfully.

    Triple DES (Data Encryption Standard): It is a symmetric encryption and an advanced form of the DES method that encrypts blocks of data using a 56-bit key.
    Triple DES applies the DES cipher algorithm three times to each data block.

    Twofish: It is a license-free encryption method that ciphers data blocks of 128 bits. Twofish always encrypts data in 16 rounds regardless of the key size.

    
#### What hashing methods do you know?

    MD5 (already broken, easy to manipulate): An MD5 hash function encodes a string of information and encodes it into a 128-bit fingerprint.
    SHA-2(Secure Hash Algorithm): The SHA-2 family consists of six hash functions with digests (hash values) that are 224, 256, 384 or 512 bits.
    CRC32: Encoding the same data string using CRC32 will always result in the same hash output.

#### How/where would you store sensitive data (like db password, API key, ...) of your application?

    Hiden from publicity. Using hashing or encryption, to further make it harder to obtain.


## Computer science


### Algorithms

#### What is the difference between Stack and Queue data structure?

    Stacks are LIFO (Last In First Out) types, which means the last inserted element
        is the first element to come out of the list. Insert operation called push and Delete is called pop.
        In stacks we maintain only one pointer to access the list, called the top (last) element.

    Queues are FIFO (Fist in First out) types, which means the first iserted element
        is the first element to come out of the list. Insert operation is called enqueue and Delete is called dequeue.
        In queues we maintain two pointer to access the list (first/last position).

#### What is BubbleSort? Describe the main logic of this sorting algorithm.

    BubbleSort is a sorting method. Starting from the first element, comparing it with the next.
    If the next element higher then the previous move to the next. Else swap them. And so on till the last index.

#### Explain the process of finding the maximum and minimum value in a list of numbers!

    Moving along the collection (iterate). Set the first as highest/lowest.
    Then comparing each next element with the firts and replace it with the first accordingly.

#### Explain the process of calculating the average value in an array of numbers!

    Adding each element value together and dividing it with the the total element count.

#### What is Big O complexity? Explain time and space complexity!

    Big O Notation is to describe the complexity of an algorithm. How long an algorithm takes to run.
    It is to compare the efficiency of different approaches to a problem. How quickly the runtime grows:
    use Big O Notation to talk about how quickly the runtime grows. Relative to the input:
    With Big O Notation, we use the size of the input, which we call “n”.
    So we can say things like the runtime grows “on the order of the size of the - input” (O(n)) or “on the order of the square of the size of the input” (O(n²)).
    As the input gets larger: we care more about the stuff that grows fastest as the input grows, because everything else is quickly eclipsed as n gets very large.

#### Explain the process of calculating the average value in a list of numbers!

    Sum all of the data values and divide by the number of nodes in the list.


### Procedural

#### How the CASE condition works in SQL?

    It is a controlling structure (like the "if" in other programming language).
    The Case statement goes through conditions and returns a value when the first condition its met.
    So once a condition is true, it will stop reading and return the result. If no coditions are true it returns the value in the else clause.

#### How the switch-case condition works in JavaScript?

    The switch statement is used to perform different actions based on different conditions.
    Use the switch stetement to select one of many code block to be executed. Instead of else we must use default.

#### How to achieve a switch-case-like structure in Python?

    The way in Python to implement switch statement is to use the powerful dictionar mapping, also known as associative arrays,
    the provide simple one to one key-value mappings.

#### Explain variable scoping in Python!

    LEGB rule!!
        L: local - Names assigned in any way within a function (def or lambda), and not declared global in that function.
        E: enclosing-function locals - Name in the local scope of any and all statically enclosing functions (def or lambda), from inner to outer.
        G: global (module) - Names assigned at the top-level of a module file, or by executing global statement in a def within the file.
        B: built-in (python) - names preassigned in the built-in name module for ex.: open, range, SyntaxError

#### What’s the difference between const and var in JavaScript?

    The const keyword created a declaration that cannot be reassigned. With var/let you can reassign and var/let is global scoped.

#### How the list comprehension looks like in Python?

    you can either use loops: spuares = [] for i in range (5) square.append(i*2) -> squares = [2,4,6,8,10]
    you can either use list comprehensions to get the same result: squares = [i*2 for i in range (5)] -> squares = [2,4,6,8,10]

#### How the “ternary expression” looks like in Python?

    result = if_true if condition else if_false

#### How the ternary expression looks like in JavaScript?

    condition ? exprIfTrue : exprIfFalse

#### How to import a function from another module in Python?

    from a import b, c

#### How to import a function from another module in JavaScript?

    import {init} from "../main.js" or
    import { htmlFactory, htmlTemplates } from "../view/htmlFactory.js";


### Functional

#### What is recursion?

    The process in which a function calls itself directly or indirectly is called recursion and the corresponding function is called a recursive function.

#### Write a recursive function which calculates the Fibonacci numbers!

     function fibo(limit, a=0, b=1) {
        if (b >= limit) {
            return
        } 
        let c = a+b; 
        console.log(c); 
        return fibo(limit,b,c)

#### How to store a function in a variable in Python?

    def one():
        print("hello") 
    function_variable = one
    function_variable()

#### List the ways of defining a callable logical unit in JavaScript!

    arrow function: const foo = (arg1, arg2) => {...};
    concie method syntax: let obj {myMethod(arg1, arg2) {...} }

#### What is an event listener? How to attach one?

    it sets up a function that will be called whenever the specified event is delivered to the target.
    documbent.getElementById("myBottun").addEventListener("click", displayDate)

#### How to trigger an event in JavaScript?

    Event listeners have a target, which they listen for. It can be triggered by:
    mouse actions, keyboard actions, content load (or changed) actions.

#### What is a callback function? Tell some examples of its usage.

    A callbach is function that will be executed after another function has finished executing - this is where it gets the name from.
    More complexly put: In JavaSricpt, functions are objects and because of this, functions can take functions as arguments,
    and can be returned by other functions.

#### What is a Python decorator? How does it work? Tell some examples of its usage.

    Decorator takes in a function, adds some functionality and returns it.
        def smart_divide(func):
            def inner(a,b):
             print("I am going to divide ",a,"and",b)
            if b == 0:
                print("whoops! connot divide")
                return func(a,b)
            return inner
        smart_devide def devide(a,b): return a/b

#### What is the difference between synchronous and asynchronous execution?

    When you execute something synchronously, you wait for it to finish before moving on to another task.
    when you execute something asynchronously, you can move on to another task before it finishes.
    Synchronous execution means the execution happens in a single series: A -> B -> C -> D.
    If you are calling those routines, A will run, then finish, then B will start, then fnish, then C will start etc.
    With asynchronous execution, you begint routine, and let it run in the backgroun while you start next, then at some point,
    say wait for this to finish. It's more like start A -> B -> C -> D -> wait for A to finish. The advantage is that you
    can execute B, C and D while A is still running (in the background, on a separate thread),
    so you can take better advantage of your resources and have fewe "hangs" or "waits".


## Programming languages


### SQL

#### How can you connect your application to a database server? What are the possible ways?

    - Need a connection string and a connection object from the database provider to set a session with the database server.
        For Python we can use the psycopg2 module api's to connect an application with psql database.
    - Everything on one server: The entire environment resides on a single server. For a typical web application, that would
        include the web server, application server, and database server.
    - Separate Database Server: The database manager system (DBMS) can be separated from the rest of the environment
        to eliminate the resource contention between the application and the database, and to increase security.

#### When do you use the DISTINCT keyword in SQL?

    DISTINCT clause is used in the SELECT statement to remove duplicate rows from a result set.

#### Talk about the behavior/goal of these base SQL clauses: WHERE, GROUP BY, HAVING, ORDER BY?

    WHERE: It'equal to if in programming languages. it's used to "filter" the data based on conditions.
    GROUP BY: the statemant groups rows that gave the same values into summary rows. It is often used with aggregate functions
        (COUNT, MAX, MIN, SUM, AVG) to group the result-set by one or more columns.
    HAVING: It is the same as WHERE. It's needed, as WHERE can not be used in aggregatin functions.
    ORDER BY: It is used to sort the result-set in ascending or descending order.

#### What are aggregate functions in SQL? Give 3 examples.

    COUNT: return the number of rows that maches a specifies criterion.
    MAX: returns the highest value of the selecter column.
    MIN: return the smallest values of the selecter column.
    SUM: returns the total sum of a numberic column.
    AVG: returns the average values of a numeric column.

#### What kind of JOIN types do you know in SQL? Could you give examples?

    INNER JOIN: returnc records at the intersection of two tables.
        SELECT first_name, last_name, order_date, oreder_amount
        FROM customers AS c.
        INNER JOIN oreder AS o. ON c.customer_id = o.customer_id
    LEFT JOIN: returns all records from table A and any matching records from table B)
        SELECT first_name, last_name, order_date, oreder_amount
        FROM customers AS c.
        LEFT JOIN oreder AS o. ON c.customer_id = o.customer_id
    RIGTH JOIN: It is a mirror version of the left join and allows to get list of all orders, appened with customer information.
    FULL OUTER JOIN: a list of all recods from both tables , we can use a full join.

#### What are the constraints in sql?

    NOT NULL - ensures that a column cannot have a NULL values
    UNIQUE - ensures that all values in a column are different.
    PRIMARY KEY - a combination of a NOT NULL and UNIQUE. Uniquely indentifies each row in a table.
    FOREIGN KEY - unequely identifies a row/record in another table.

#### What is a cursor in SQL? Why would you use one?

    A CURSOR IS A TEMPORARY WORK ARE CREATED IN THE SYSTEM MEMORY WHEN A SQL STATEMENT IS EXECUTED.
    THIS TEMPORARY WORK AREA IS USE TO STORE THE DATA RETRIEVED FROM THE DATABASE, AND MANIPULAT THIS DATA.

    A cursor contains information on a select statement and the rows of data accessed by it.    
    A cursors can hold more then one row, but can process only one row at a time. The set of rows the cursor holds is called the active set.

#### What are database indexes? When to use?

    A database index is a data structure that improves the speed of data retrieval operations on a database table at the cost of addtitional writes
    and storage space to maintain te index data structure. Indexes are used to quickly locate data without having to search every row
    in a databas table.

#### What are database transactions? When to use?

    DATABASE TRANSACTION IS AN INVISIBLE UNIT OF WORK. for exaple which I DELETE from one table I have to INSERT INTO another.
    A TRANSACTION IS A UNIT OF WORK THAT YOU WANT TO TREAT AS A WHOLE. IT HAS TO EITHER HAPPEN IN A FULL OR NOT AT ALL.

    A classical example is transferring money from one bank account to anouther. The operation has to succeed in full. If you stop halfway, the mondey will be lost.

    ACID = Atomic (all run or not at all), Consistent (not leaving mess behind), Isolated (during the tansaction nothing else can make a change), Durable (change made persist)

    How look like in SQL:
    CREATE PROCEDURE ArchiveStudents(@Graduation INT)
    AS
    BEGIN TRY
        BEGIN TRANSACTION
                INSERT INTO StudentsArchive(StudentId, FristName, LastName, Graduation)
                SELECT * 
                FROM students 
                WHERE Graduation < @Graduation

                DELETE FROM Students
                WHERE Graduation < @Graduation
        COMMIT TRANSACTION
    END TRY
    BEGIN CATCH
        ROLLBACK TRANSACTION
    END CATCH
    
#### What kind of database relations do you know? How to define them?

    One-to-One: A row in A table can have only one matching row in talbe B, and the other way around as well.
    One-to-Many ( or Many-to-One): This is the most common relationship type. In this type of relationship, a row in A table can have many matching rows in table B,
        but a row in table B can only one matching row in table A (Each costumer can only be assignes to one city. One city can be assignes to many costumer).
    Many-to-Many: relationship could be thought of as two one-to-many relationships, linked to an intermediary table (cross-referene table).
        for example: in order to create a many-to-many realitonship between customers table and the product table, we create a new table called Oders

#### You have a table with an “address” field which contains data like “3525, Miskolc, Régiposta 9.” (postcode, city, street name and address). How would you query all records related to Miskolc?

        SELECT *
        FROM table
        WHERE adress LIKE '%Miskolc%';

#### How would you keep track of what kind of data has changed after an UPDATE or DELETE operation in a table?

    I would create a person_log table and create a trigger on that will insert a row into person_log table whenever a table(s)
    or row(s) get updated/deleted/added.


### HTML & CSS

#### What’s the difference between XML, XHTML and HTML?

    both are markup languages, which represents text data in proper format by using tags. However they are used for completely different purposes.
    Similarities between HTML and XML: both are languages of web and both are markup languages. Both are originated from
        SGML (Standardized General Markup Language). Tags are basic building block of both. 
    Differences: HTML FOCUSES ON HOW DATA LOOKS LIKE, WHERE AS XML FOCUESES ON WHAT THE DATA IS.
        tags are predefined where as XML tags are user defined tags. HTML tags are limited number or tags
        where as XML tags are extensible. HTML tags are case insensitive where as XML tags are sensitive.
        HTML tags are menat for displaying the data but not for describing it, where as XML tags are meant for describint the data.
    XHTML (Extensible HyperText Markup Language) is almost identical to HTML. It is stricter then HTML.
        It is HTML defined as an XML application.

#### How to include a JavaScript file in a webpage?

    Using the script tag in .html header:
    <script type="text/javasrcript" scr="path-to-javascript-file.js" defer></script>

#### How to include a CSS file in a webpage?
    
    Using the link tag in .html file
    <link rel="stylesheet" href="{{ url_for('folder-where-the-SCC-is', filename='style/form.css') }}">

#### How to select an element using its id in CSS?

    you have to use the hashtag (#) + the element id name

#### How to select elements using their class in CSS?

    you have to use the dot (.) + the element class name

#### How to select elements which have the ‘alpha’ and ‘beta’ classes in CSS?

    .alpha {...} 
    .beta {...}

#### How to select all list items in all ordered lists on the page in CSS?

    you can reach by using the ordered tag wich is "ol": ol li {...}

#### How to select elements using their attributes in CSS?

    [attribute] = selector is used to select elements with a specified attribute.
    [attribute="value"]= selector is used to select elements with a specified attribute and value.
    [attribute~="value"] = selector is used to select elements with an attribute value containing a specified word.
    [attribute^="value"] = elector is used to select elements with the specified attribute, whose value starts with the specified value.
    [attribute|="value"] = selector is used to select elements with the specified attribute, whose value can be exactly the specified value.
    attribute$="value"] = selector is used to select elements whose attribute value ends with a specified value.

#### What are UX and UI?

    UI: IT STAND FOR "USER INTERFACE". IT IS THE GRAPHICAL LAYOUT OF AN APPLICATION.
        It consists of the button, that users click on, the text they read, the images, sliders, text entry fields, and all the rest
        of the items the user interacts with. This includes screen layout, transistion, interface animation and every single micro-interaction.
        Any sort of visual element, interaction or animation must all be designed.

    UX: IT STANDS FOR "USER EXPERIENCE".IT IS DETERMINED BY HOW THEY INTERACT WITH IT.
        It is also determined by how easy to interact with the user interface elements that the UI designer have created.

#### Please list some points that an application should fulfill to have good UX.

    Usefullness, Useability, Desireable (more attractive)
    Meets the users's needs, have a clear hierarchy, consistency understand, accessibility, usability

#### What is XML, XSLT, DTD?

    HTML is an application of SGML (standard Generalized Markup language). XML is simplified subset of SGML.
    DTD (Ducoment Type Declaration) is a set of instructions that states what tags are useable and what reaction they create.
        Each browser has DTD set in its programming set by the browser companies. This is how some tags will work in only one type of browser or version.
        It has the tags stated in its DTD.
    XML makes it possible to create unique tags sets by appliying its own DTD. This makes DTD more compactable with more browser.
    XSLT (sXtensible Srylesheet Language Transformation): It is a strong version of CSS that formats the XML page for viewing.

#### What is the difference between HTML and XML?

    HTML FOCUSES ON HOW DATA LOOKS, WHERE AS XML FOCUESE ON WHAT THE DATA IS.
    HTML tags are predefined tags, where as XML tags are user defined tags. HTML tags are limited number of tags, where as XML tags are extensible.
    HTML tags are case insensitive where as XML tags are sensitive. HTML tags are meant to displaying the data but not for
    describing the data where as XML tags are meant for descriping the data. 

### Javascript

#### What is javascript?

    JS is a scripting laguage designed to control web page content. It can update and change both HTML and CSS.
    It can calculat, manipulate and validate data.

#### When to use AJAX? Bring examples of its usage.

    AJAX stands for Asynchronous Javascript and XML.
        AJAX programming is used, for exchanging data in the background without actually reload the page and distrubing the user experience.
        It renderes the access of data more efficiently.
    Form validation: It's so much nicer when the form tells you as you are typing if you'have filled it ou wrong or not.
    Comments: when a commenter hits the comment button, it's nice to see the comment appear immediately on the page.
    login forms, Auto-Complete (when searching for example), Voting and Rating, Updating With User Content

#### What is DOM and how to manipulate it from Javascript?

    DOM (Document Object Model) is representative diplaying for the according HTML document, and those object can be modified.
    Creating, removing or replacing an element, Modifying an element' text and/or HTML content. Getting an element contetnt and working with it.

#### What are events and how/why to use them in Javascript?

    for example an event occur when the page loads. also can be triggered manually too, when user interact (clicks, hovers, changes).
    The addEventListener method is the most preferred way to add an event listener to window, document or any other element in the DOM,
    becaue JavaScript in the browser uses an event-driven programming model. Everything stats by following an event.

#### What is event bubbling/capturing? How would you use it?

    Event bubbling and capturing are two ways of event propagation in the HTML DOM API.
    When an event occurs in an element inside another element, and both elements have registered an event.
    When an event happens on an element, it first runs the handles on it, then on its parent, then all the way up on other ancertos.
    With capturing, the event is first captured by the outermost element and propagated to the inner element.

#### What is JSON and how do we use it?

    JSON is a short for JavaScrip Object Notation, and it is a way to store information in an organized, easy-to-access manner.
        In a nutshell, it gives us a human-readable collection of data that we can access in a really logical manner.
        JSON (in JavaScript) is a string.
    How to use it: in short, you are forced to comminacate things using key-value pairs and arrays.
        JSON is basically a way of communicatin data to someone, with very specific rules.


## Software engineering

### Version control

#### What type of branching strategy would you use?

    Code in master/development is deployable at all times. When you want to start working on a new task, you should create a new branch off
    of master/development and give it a descriptive name. Commit to that branch localy and regularly send my work to the same-named branch on the server.
    Open a pull request when you feel your changes are ready to be merged (or even if you aren't so sure, but would like some feedback).
    After the new feature is revised and approved, you can merge it into master/development. Once my changes are merged and pushed to the master/development
    I would delete that branch.

#### What would you do if you find a bug on the production code (master branch)?

    I would report it to my project manager, and she/he would tell us how or who should fix it.
    Alternatively, I would open a new branch, locate and fix the bug and after testing, I would merge it back to the master/development.

#### How can you move changes from one branch to another in GIT?

    Create and checkout to a new branch will copy the actual state of the original branch where can be rollback or set back status.
    Otherwise Rebase or merge bring changes from another branch into the current one.

#### How does a VCS help with code reviews?

    Modern version control system are designed to help adress problems that teams face when collaborating.
    Breaking down walls and see more prespectives and conversations can enable you and your team to deliver better software.

#### What is your favorite git command? Why?

    Git merge: becuase that means I am ready with my task well, so I can merge into the master/development branch.

#### What does remote/local mean in Git? 

    Remote: Repository's server ther storing the repo online
    Local: The repository's offline, local, on-disk sotred version, which we make the changes on.


### DevOps

#### Why is it good to use a package manager software?

    pip, npm, Maven

    A package manager is a programming language's tool to create project environments and easily import external dependencies.
    You don't have to reinvent the wheel and able to make the most of the tools at your disposal.
    When working on a project or library, you may package your project and publish it for others.

    In this case a new developers come onto your project, team, company they are likely to know the converntions of the package manager.
    This means they don't have to waste time figuring out the fine detalis of how libraries are managed in you code base.

    Some package managers provide additional features during installation. They tend to centralize hostin and distribution.
    Help with complex dependency trees and that can be managed downloading a dependency together with all its dependencies.
    Packages contain metadata, such as the software's name, description of its purpose, version number, vendor, checksum,
    and a list of dependencies necessary for the software to run properly.

#### Why is it good to use a virtual environment for a project?

    Dependency Management: prevent conflicts between dependencies of multiple project.
    Even a project can have a single unique virtual environment with the specifit packages.


### Networks

#### What kind of HTTP status codes do you know?

    - 200: OK
    - 301: Moved Permanently
    - 302: Found
    - 400: Bad Request
    - 401: Forbidden
    - 404: Not Found
    - 405: Method Not Allowed
    - 408: Request Timeout
    - 500: Internal Server Error
    - 504: Gateway Timeout

#### What is an API?

    API (Application Programming Interface) is sessentailly a way for apps to borrow functionality and data from each other.
    An API allows two software programs to communicate with each other. One program can call another programs API to get acces to
    data or functionality of the other program. An API is the messenger that takes a request, tells a system what you want to do
    and then returns the response back to you.

#### What is REST API?

    A REST API uses HTTP requests to GET, PUT, POSR, and DELETE data.
    It's a simple and standardized software architecture style, a specific type of API.
    restful web service is a service that uses REST APIs to communicate.


#### What is JSON? When to use?

    JSON (JavaSricp Object Notation) is a way to store information in an organizes, ready-to-access manner.
        In a nutshell, it gives us a human-readable collection of data that we can access in really logical manner.
        JSON (in JavaScript) is a string.
    How to use it: In a short, you are forced to communicate things using key-value pairs and arrays.
        JSON is basically a way of communicating data to someone, with very specific rules.
        For fast and effective communication between server-user for example.

#### What is TCP/IP? What layers does it define, what are they responsible for?

    IT'S LIKE A SET OF RULES TO ALLOW COMPUTERS TO COMMUNICATION BETWEEN EACH OTHER. IT GARANTES YOU THAT YOU RECIEVE ALL THE DATA IN THE RIGHT ORDER
    Transmission Control Protocol/Internet Protocol (TCP/IP) is the language a computer uses to access the internet. In consists of a suite of
    protocols designes to establish a network of networks to provide a host with access to the internet.

#### What’s the difference between TCP and UDP?

    TCP (Transmission Control Protocol) is connection oriented protocol, where as UDP (User Datagram Protocol) is connection-less.
    - TCP first must actknowledge a session between the two computer that are communicating. They verify a connection before communicating.
        TCP track all data sent and guarantee all the data is recieved.
    - UDP (fire and foreget protocol) does not use actknowledgment at all. It doesn't create session between two computers and doesn't guarantee all the data will be recieved.
        and it usually used for protocols where a few lost datagrams do not matter. If data is missing the reciever ask for more data.
    UDP is faster than TCP

#### How does an HTTP Request look like? What are the most relevant HTTP header fields?

    A simple request message from a client computer consists of the following component:
        - a Request-line -> to get required resorce (Request-Line = Method SP Request-URI SP HTTP-Version CRLF)
            The elements are separated by space SP characters. Method=GET/POST/PUT/DELETE... .  Request-URI = "*" | absoluteURI | abs_path | authority
        - Header (General|Request|Entity) fields:
            Host, User-Agent, Accept, Accept-Language, Accept-Encoding, Connection
        - an empty line 
        - optionally a message-body

#### How does an HTTP Response look like? What are the most relevant HTTP header fields?
    # A simple response from the server contains the following somponents: HTTP Status code (for ecample: HTTP/1.1 301 Moved Permanently,
        means the requested resource was permanently moved and redirecting to some other resource.)
        Headers (example - Condent-Type: html) an empty line. A message body which is optional.

#### What is DNS? How does it work?
    # Domain Name Servers (DNS) are the Internet's equivalent of a phone book. They meintain a directory of domain names
        and translate then to Internet Protocol (IP) adresses.

#### What is a web server?
    # A web server is a program that uses HTTP to serve the files that form Web pages to users, in response to their requests, which are
        forwarded by their computers' HTTP clients. Dedicated computer and appliances may be referred to as Web servers as well.

#### Explain the client-server architecture.
    # It is an architecture os a computer network in which many clients (remote processors) request and recive service from a centralized sever (host computer)
        Client computers provide an interface to allow computer user to request service of the server and to diplay the results the server returns.

#### What would you use a session for?
    # The purpose for session is to store that you (as the web application developer) would like to have preserved across page loads.
        On this, you can set glags in your login script such as logged_in, to check if the user is logged in, and on any other page
        check seccion['logged_in'] == true, insted of querying for that information. Session use a cokie as a key of sorts,
        to associate with the data that is stored on the server side. Session variables will be expires when users close the browser.
        

#### What would you use a cookie for?
    # You can save setting to cookie for the websites between visits, so its going to remember your previous preferences.
        Cookies soterd on web-borwser (client-sie) not very safe, since the hackers can reach and get your information.
    Expiration can be set (see setcookies() for more information)


## Software Development Methodologies


#### What kind of software development methodologies do you know? What are the main features of these?
    # Waterfall development methodology: Requirements -> Desing -> Implementation -> Verification -> Maintanance.
        It's a rigid linear model that consists of sequential phases (requirements, design, implementation, verification, maintence)
        in which distict goals are accomplished. Each phase must be 100% complete before the next phase can start,
        and traditionally there is no process for going back to modify the project or direction.
    # Agile: Adaptive approach which is able to respond to the changing requirements of the cliendts. Direct communication and feedback from customer.
        Agile development methodology: Requirement/Feature/User stories/Product Backlog -> Scrum team (with lead) -> Sprint ->
        Planning -> Spring 1-4 weeks duration -> Production deployment ->
        Done Checklist (While this process other people making the design, build it, inegrate, test the software) -> Sprint Retrospective ->
        Product review (costumer input) -> Potential Product Increment.

#### What are the SCRUM roles?
    # One of the most important things for the success of SCRUM is the role of the Product Owner, show serves as an interface between
        the team and other involved parties (stakeholders). The Scrum Master does not interfere into the decisions of the team regarding
        specifically the development, bur rather is there for the team as an advisor. he only interferes actively when anybody of the team or
        any other participant of a project (stakeholder) does not obey the rules of SCRU. The development Team in SCRUM a team is not just
        the executive organ that receives its task from the project leader, it rather decides self dependent, which requirement or Users Stories
        it can accomplish in on spring.

#### What are the SCRUM ceremonies?
    # Ceremonies Sprint, Planning Sprint, Review Sprint, Retrospectitive Daily SCRUM

#### What are the SCRUM artifacts?
    # Artifacts: Incerment, Product backlog, Sprint backlog

#### What is the main goal of a retrospective meeting?
    # This is where the Scrum Team meets to reflect on their previous Spring and to figure out how to improve as a team by asking:
        What went well? - What did not go well? - What can be improved?.
        It allows the team to focus on its overall performance and identify strategies for continuous improvement.

#### Explain, when would you recommend to use the waterfall methodology?
    # Use waterfall when the project is simple or the project is complicated, but you have the expertise to deliver it. It is all you know and you have no support for change.
        The upfont invesment is not risky to make, you focus your performance measures on delivery date and budget.
