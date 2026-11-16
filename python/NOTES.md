# Python for a JavaScript developer

Five things that are different in Python for the same Reading List functions (`books.py`):

1. **Blocks and lists:** Python uses indentation and a colon instead of `{ }` to mark a block, and our filter is a plain `for book in books:` loop that adds matches with `result.append(book)`, which is Python's `push()`.
2. **String methods:** `trim()` is `strip()`, `toLowerCase()` is `lower()`, and `title.includes(q)` becomes the `in` keyword, so the search line is `normalized_query in book.title.lower()`.
3. **Operators and nothing:** `&&`, `||` and `===` are written `and`, `or` and `==`, and `null` is `None`, so a rating of `number | null` becomes `Optional[int]`.
4. **Objects:** a book is a `@dataclass` class read with `book.title`, while the result of `validate_book` is a `dict` read with `errors["title"]`; that dict only gets a key when a field is invalid, so an empty `{}` means valid, just like in TypeScript.
5. **Types:** the biggest difference is that Python never checks type hints when the code runs, so `filter_books(books, "all", 42)` starts and only crashes at `.strip()`, where TypeScript would refuse to compile; in Python, the tests are what protect you.
