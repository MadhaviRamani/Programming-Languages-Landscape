# Java for a JavaScript developer

Five things that are different in Java for the same Reading List functions (`src/Books.java`):

1. **Everything lives in a class:** Java has no free functions, so `filterBooks` and `validateBook` are `static` methods of the class `Books`, every parameter and return value has a type written in front (`static List<Book> filterBooks(List<Book> books, String status, String query)`), and the code must be compiled with `javac` before it can run.
2. **String methods:** `trim()` is `strip()`, `includes()` is `contains()`, and `toLowerCase()` takes a `Locale.ROOT` argument, because without it the result depends on the language of the computer (in Turkish, `"TITLE"` becomes `"tıtle"` with a dotless i).
3. **Comparing strings:** `===` is `equals()`, as in `status.equals("all")`, because `==` on two strings only checks whether they are the same object in memory, not whether they have the same text.
4. **Lists and objects:** our filter is a `for (Book book : books)` loop (Java's `for...of`) that fills a new `ArrayList` with `add()`, Java's `push()`; a book is a `record`, a short immutable class read with `book.title()`, and the errors are a `Map` filled with `put("title", ...)`, so an empty map means valid, like the empty `{}` in TypeScript.
5. **Types and `null`:** the compiler checks every type before the code runs, so `filterBooks(books, "all", 42)` does not compile, just like in TypeScript; but any object can still be `null` without a warning, so a rating that can be missing is an `Integer` (an object that can be `null`) instead of an `int` (a number that can not), and our functions return an empty list or map instead of `null`.
