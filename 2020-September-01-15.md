# Clojurists Together Q3 - Practicalli - Update 2
Invested time to understand the changes coming to the Clojure CLI tools and understand the opportunities that [Clojure exec](https://insideclojure.org/2020/09/04/clj-exec/) (`:exec-fn` & `:exec-args`) brings to aliases. These changes provided a catalyst to start redesigning the aliases used in [practicalli/clojure-deps-edn](https://github.com/practicalli/clojure-deps-edn/tree/qualified-alias-keywords-and-new-flags).


## Practicalli Study Group
Continuing the Banking on Clojure project, especially around database access.  The database schema was refined along with improved approaches to creating database schema, using transactional updates and ensuring connections are closed.  The next.jdbc friendly functions were explored and a CRUD approach implemented.

- [082 - Banking On Clojure - Part3 - next.jdbc for SQL in Clojure](https://youtu.be/sBdmwDUp1Ho)
- [083 - Banking On Clojure - Part4 - Updating data in the database](https://youtu.be/DmYlNTe7Gds)

Next steps will be to use Clojure spec for generative testing with the database, add connection pooling and using lifecycle management libraries.


## Practicalli WebApps
Updated sections on [H2 Database](https://practicalli.github.io/clojure-webapps/relational-databases-and-sql/h2-database/) and Banking on Clojure

- [Design and Create Database Tables](https://practicalli.github.io/clojure-webapps/projects/banking-on-clojure/database-tables.html)
- [Defining Database Queries - different approaches](https://practicalli.github.io/clojure-webapps/projects/banking-on-clojure/database-queries.html)
- [Create database records](https://practicalli.github.io/clojure-webapps/projects/banking-on-clojure/create-records.html)
- [Read Database Records](https://practicalli.github.io/clojure-webapps/projects/banking-on-clojure/read-records.html)
- [Update Records in the database](https://practicalli.github.io/clojure-webapps/projects/banking-on-clojure/update-records.html)
- [Delete Records in the database](https://practicalli.github.io/clojure-webapps/projects/banking-on-clojure/delete-records.html)


## Practicalli Clojure
Added [core principles for writing effective unit tests](https://practicalli.github.io/clojure/testing/unit-testing/) in Clojure. Included project configuration examples of unit tests for Leiningen and Clojure CLI tools.  Also included example configuration for Emacs CIDER test runner and link to the test runner configurations in [practicalli/clojure-deps-edn](https://github.com/practicalli/clojure-deps-edn/tree/qualified-alias-keywords-and-new-flags).


## Clojure deps.edn
Created a [draft guide to changes in the next release of the Clojue CLI tools](https://gist.github.com/jr0cket/ae7dd745eb45870109ace59fe835ce80), to understand the significance of the changes it introduces.  The `-X` flag for executing a function with EDN arguments (hash-map arguments) has already been introduced and the new release depreciates the generic `-A` alias in favor of `-M`.  In the long term using the `-X` flag with functions that take a structured argument looks to be an excellent approach.

Started a [redesign of practicalli/clojure-deps-edn using qualified keywords for alias names](https://github.com/practicalli/clojure-deps-edn/tree/qualified-alias-keywords-and-new-flags).  The Library repositories keyword, `:mvn/repos`, is already qualified, so this redesign brings the aliases in line with that style.  The alias keywords are prepended with names to communicate the category of purpose for each alias, e.g. repl, project, env, lib, inspect, build, deploy.

As part of the redesign, the new flags introduced with Clojure CLI tools, `-M` and `-X`, are used.  The `-X` flag is the preferred Clojure command line flag to use for the aliases, where the library supports executing a function from the library that takes a hash-map of arguments.  Otherwise `-M` flag replaces `-A` flag and continues to use `clojure.main` to call the `-main` function of the given main namespace.

Add project/check to give detailed report on compilation issues for a project


## Practicalli Spacemacs
Resolved simple bug fixes raised by the community.
