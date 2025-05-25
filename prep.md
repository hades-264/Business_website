## Quiz Summary: Java, JSP, JDBC, SQL, and Web Concepts

**Your Overall Score:** 81 out of 92 questions correct (approx. 88.04%)

---

### I. SQL Concepts

* **DDL (Data Definition Language):**
    * **Q1:** Full form of DDL is "Data Definition Language".
    * **Q5:** `DROP TABLE student;` deletes the table named `student`.
* **SQL Constraints:**
    * **Q10, Q28:** The `DEFAULT` constraint sets a value for a field if one isn't explicitly provided during insert.
* **Triggers:**
    * **Q34:** Triggers can be executed `BEFORE`, `AFTER`, or `INSTEAD OF` a DML event.
    * **Q29:** Asynchronous table replication is generally not considered a direct advantage *of* triggers themselves (other options like auto-generating values, validation, maintaining integrity are).
* **Joins:**
    * **Q59:** A table joined with itself is called a **Self Join**.
* **Cursor Attributes (PL/SQL):**
    * **Q64:** `%FOUND` returns `TRUE` if an `INSERT`, `UPDATE`, or `DELETE` statement affected one or more rows.
    * **Q52:** The quiz material suggested "2" general types of cursors (e.g., implicit/explicit or forward-only/scrollable).
* **SQL Data Types:**
    * **Q15:** "Character" as a standalone type name might not be valid in all SQL RDBMS compared to `FLOAT`, `NUMERIC`, `DECIMAL` (SQL often uses `CHAR` or `VARCHAR`).

---

### II. Core Java Concepts

* **Fundamentals:**
    * **Q6:** The default access modifier for class members (if none is specified) is package-private (often just called "default" access).
    * **Q9:** Class names can contain letters, digits (not as the first character), underscores, and dollar signs. They cannot be Java keywords.
    * **Q19:** The `final` keyword:
        * Prevents method overriding.
        * Prevents class inheritance (subclassing).
        * Makes variables assignable only once.
    * **Q78:** The `break` statement is used to immediately terminate a loop.
    * **Q82:** Correct for-each loop syntax: `for (String name : namesList)`.
    * **Q89:** Arrays are passed by reference in Java, so modifications within a method affect the original array. (Example: `x[1] = x[1] * 2;` changed `a[1]` from 1 to 2).
* **Object-Oriented Programming (OOP):**
    * **Q30, Q60:** Inheritance (`class SubClass extends SuperClass`) is primarily used to create a new class from an existing class, allowing for shared structure and behavior (code reusability, "is-a" relationship).
    * **Q32, Q48, Q65:** Polymorphism allows a single action (method call) to be performed in different ways depending on the object's actual type (e.g., method overriding).
* **Collections Framework:**
    * **Q4, Q12, Q72:** `ArrayList` allows dynamic storage of elements. `players.get(2)` retrieves the element at index 2 (0-indexed). Attempting to cast an incompatible type from an `ArrayList` (e.g., String to int) causes a `ClassCastException` (Q12).
    * **Q61:** `ArrayList` has a `size()` method (number of elements), but not a `length()` method.
    * **Q40:** `HashMap.get(key)` returns `null` if the key does not exist.
    * **Q42:** `Collections.sort()` for larger lists often uses Merge Sort or a hybrid like Timsort.
    * **Q20:** Collection classes are primarily in the `java.util` package.
* **Exception Handling:**
    * **Q36:** `Throwable` is the superclass of all errors and exceptions.
    * **Q7:** `Error` and its subclasses represent serious problems an application shouldn't typically try to catch (e.g., `OutOfMemoryError`).
    * **Q38:** Example: `10/0` throws `ArithmeticException`, which can be caught.
    * **Q37:** The `finally` block ensures cleanup code executes regardless of exceptions.
    * **Q74:** Primary purpose is to handle runtime errors and maintain the normal flow of the program.
    * **Q24:** `RuntimeException` can catch its subclasses like `ArithmeticException`.
* **String Manipulation:**
    * **Q58:** `word.contains("substring")` returns `true` if the string contains the substring (e.g., "Automation".contains("u") is true).
* **File I/O:**
    * **Q57:** `new File("path")` creates a `File` object (abstract path). Physical file creation typically uses `file.createNewFile()`. `new FileWriter("path")` or `new PrintWriter("path")` will create the physical file if it doesn't exist.
* **Loops:**
    * **Q26:** A `while` loop without updating the loop variable can lead to an infinite loop.

---

### III. JDBC (Java Database Connectivity)

* **Core Components & Setup:**
    * **Q47, Q68, Q84:** `DriverManager.getConnection()` establishes a database connection.
    * **Q43, Q49, Q51:** `Class.forName("driver.class.name")` was used to load JDBC drivers (especially pre-JDBC 4.0). The primary purpose of a JDBC driver is to enable Java applications to connect and interact with databases.
    * **Q44:** Example of connecting to SQLite: `Class.forName("org.sqlite.JDBC"); Connection con = DriverManager.getConnection("jdbc:sqlite:DB_PATH");`
* **Executing Queries:**
    * **Q23, Q67, Q81:** `PreparedStatement` is used for parameterized (dynamic) SQL queries, which helps prevent SQL injection, and is suitable for INSERTs, UPDATEs, DELETEs, and SELECTs.
    * **Q8, Q41, Q55:** `executeQuery()` is used for SQL statements that return a `ResultSet` (typically `SELECT` queries).
    * **Q17, Q70:** `executeUpdate()` is used for DML (`INSERT`, `UPDATE`, `DELETE`) and DDL statements.
    * **Q22:** To execute a `PreparedStatement` that is a SELECT query and get a `ResultSet`, you call `executeQuery()`.
* **Handling Results:**
    * **Q56, Q87:** `ResultSet` object holds query results. Use methods like `rs.getInt(columnIndexOrName)` or `rs.getString(columnIndexOrName)` to retrieve data.
* **Resource Management:**
    * **Q88:** Database connections (e.g., `Connection c`) are closed using `c.close()`.

---

### IV. JSP (JavaServer Pages)

* **Scripting Elements:**
    * **Q62:** JSP Declarations (`<%! ... %>`) are for declaring class-level variables and methods in the generated servlet.
    * **Q75:** JSP Scriptlets (`<% ... %>`) allow embedding Java code within the `_jspService()` method for request processing.
    * **Q16, Q77, Q79, Q93:** JSP Expressions (`<%= ... %>`) evaluate a Java expression and print its string value into the output. They do not end with a semicolon (Q16). `Q93` asked to identify this tag. `Q77` example: `<%= new java.util.Date() %>` prints current server date/time.
* **Directives:**
    * **Q11:** `page`, `include`, `taglib` are JSP directives. "command directive" is not.
    * **Q80, Q86:** `<%@ page import="className" %>` is used to import Java classes.
* **Standard Actions:**
    * **Q69:** `<jsp:useBean />` typically requires `id` and `class` attributes to define and instantiate a bean.
* **Comments:**
    * **Q21:** HTML comments (``) are sent to the client; JSP comments (`<%-- --%>`) are server-side only and not sent to the client. They are not interchangeable for the same effect.
* **JSP Lifecycle:**
    * **Q13:** `jspInit()` is called only once during the JSP lifecycle. (You also received a brief explanation of the full lifecycle).

---

### V. Servlets

* **Fundamentals:**
    * **Q63:** Servlets are server-side Java components.
    * **Q31, Q53:** URL mapping can be done using `@WebServlet("/path")` annotation or in `web.xml` using patterns like `/path`, `*.extension` (e.g., `*.do`), or `/` (default servlet).
* **Request & Response Handling:**
    * **Q3, Q33:** `doGet()` handles HTTP GET requests. Parameters are often extracted using `request.getParameter()`.
    * **Q14:** HTTP GET method appends data to the URL.
    * **Q18:** HTTP GET sends encoded user info in URL and is often the default method for browser requests.
    * **Q27:** `response.setContentType("text/html")` sets the response content type.
    * **Q25:** `PrintWriter` (obtained via `response.getWriter()`) is used to send character-based content (like HTML) to the client.
    * **Q71:** `response.sendRedirect("url")` redirects the client to a new URL.
    * **Q91:** `RequestDispatcher.forward(req, res)` transfers control to another resource. Output from the original servlet is typically cleared, and only the forwarded resource's content is sent.
    * **Q39:** Form data from GET requests is retrieved using `request.getParameter()`.
* **Session Management:**
    * **Q2:** Cookies are stored on the client-side for session management.
    * **Q54, Q66, Q92:** `HttpSession` objects are used to maintain user-specific session data across multiple requests. Obtain via `request.getSession()`. Retrieve attributes using `session.getAttribute("name")`.

---

### VI. JavaScript (Noted as somewhat out of place in a Java-centric quiz)

* **Q73:** Loose equality `==` in JavaScript: `"111" == 111` evaluates to `true` due to type coercion.
* **Q83:** Strict equality `===` in JavaScript: `111 === "111"` evaluates to `false` because types are different.

---

### VII. General Web Application Concepts

* **Q85:** For features like displaying bestsellers in a Java web application, Servlets and JSP are a suitable combination.

---

**Note:** Question 90 (regarding Hybrid Inheritance) was skipped as the necessary diagram/code was not provided.

This summary should help you focus on the key concepts from our quiz session. Keep up the great work with your preparation!