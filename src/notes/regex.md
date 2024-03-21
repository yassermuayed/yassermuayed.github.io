# Regular expressions

Regular expressions is a powerful way of doing search and replace in strings.

In JavaScript they are available via the RegExp object, as well as being integrated in methods of strings.

## Patterns and flags

**Regular expression**  (also “regexp”, or just “reg”) consists of a pattern and optional flags.

```javascript
regexp = new RegExp("pattern", "flags");
```

```javascript
regexp = /pattern/; // no flags
regexp = /pattern/gmi; // with flags
```

Slashes syntax does not allow expression insertion (like template literals in sting)

**Flags** affect the search. There are 6 of theme:

1. `i` case-insensitive
2. `g` all matches(not just the first)
3. `m` multiline mode
4. `s` “dotall” mode
5. `u` unicode support
6. `y` Sticky

Regular expressions are integrated with string methods.

*Searching: str.match*
*Replacing: str.replace*
*Testing: regexp.test*
