## 1. Common Naming Patterns

Naming is crucial for readable and maintainable code. Try to be consistent in the naming style throughout your code.

### **1.1 Do**
* `IsX`: Often used for naming logic variables to ask a question (for example, `IsEmpty`).
* `OnX`: An overloadable function called by the framework.
* `SubscribeX`: Subscribe to framework event named X, often passing an `OnX` function to it.
* `MakeC`: Make an instance of class c without overloading the c constructor.
* `CreateC`: Create an instance of class c, beginning its logical lifetime.
* `DestroyC`: End the logic lifetime.
* `C:c`: If you’re working with a single instance of class c, it’s fine to call it C.

### **1.2 Don’t**
* Decorate type names. Just call it `thing`, not `thing_type` or `thing_class`.
* Decorate enumeration values. Not `color := enum{COLOR_Red, COLOR_Green}`, use `color := enum{Red, Green}`.
  

***

## 2. Names

### 2.1 Types use lower_snake_case
Type names should always be lower_snake_case. This includes all types: structs, classes, typedefs, traits/interfaces, enums, etc.

`my_new_type := class`

### 2.2 Interfaces are adjectives
Interfaces should be adjectives where possible, such as printable, enumerable. Where adjectives don’t seem right, append `_interface` to the name instead.

`my_new_thing_interface := interface`

### 2.3 PascalCase everything else
All other names should be PascalCase. Modules, member variables, parameters, methods, and so on.

`MyNewVariable:my_new_type = …`

### 2.4 Parametric Types

* Name parametric types t or thing, where thing explains what the type is supposed to represent. For example: `Send(Payload:payload where payload:type)` You’re sending some parameterized data, `Payload`, of any `payload` type.
* If there’s more than one parametric type, avoid using single letters, such as `t`, `u`, `g`
* Never use `_t` suffix.

***

## 3. Formatting

It is important to stay consistent with formatting throughout your codebase. This makes the code easier to read and understand for yourself and other developers. Choose a formatting style that works for the project.

As an example of staying consistent, you could choose one of the following spacing formats and use it throughout the codebase:

* `MyVariable : int = 5`

* `MyVariable:int = 5`

### 3.1 Indentation

 Use four spaces for indentation, never tabs.
 Code blocks should use indented blocks (spaced) rather than curly brackets (braced):

![3-1](https://github.com/LilWikipedia/UEFNVersePocketWiki/assets/78571191/c4b29e5b-3296-441a-a94d-431501eb0e8d)

Except when writing single line expressions like `option{a}`, `my_class{A := b}`, etc.

### 3.2 Spaces

 Use spaces around operators, unless it makes sense to keep the code compact for its context. Add braces to explicitly define the order of operations.

`MyNumber := 4 + (2 * (a + b))`

 Don’t add spaces at the beginnings and ends of brackets. Multiple expressions inside brackets should be separated by a single space.

![3-2 b](https://github.com/LilWikipedia/UEFNVersePocketWiki/assets/78571191/07b11859-1db5-40cf-9d8d-4f2e10d89485)

Keep identifier and type together; add a space around the assignment `=` operator. Add a space around type definitions and constant initialization operators (`:=`).

*  ` MyVariable:int = 5`
*  ` MyVariable := 5`
*  ` my_type := class`

Follow the same recommendations for brackets, identifiers, and types spacing for function signatures.
![3-3C](https://github.com/LilWikipedia/UEFNVersePocketWiki/assets/78571191/097ed183-b7a7-4f22-8ffa-e7bdc802fae2)

### 3.3 Line Breaks

* Use a spaced, multiline form to insert a line break. For example:

![LINE](https://github.com/LilWikipedia/UEFNVersePocketWiki/assets/78571191/1afb31d0-2b71-4118-856b-ab50cbcdddb4)

* DO NOT use a single line, example:

`MyTransform := transform{Translation := vector3{X := 100.0, Y := 200.0, Z := 300.0}, Rotation := rotation{...}}`

* Define enums in spaced, multiline form if they need per-enumeration comments or if you need to insert a line break.

`  enum:`

`      Red, # Desc1`

`      Blue, # Desc2`

### 3.4 Brackets

* Only use brackets for inheriting class definitions. For example:

`my_base_type := class:`

* Do NOT use this styling:

`my_base_type := class():`

### 3.5 Avoid Dot-Space Notation

* Avoid using dot-space ". " notation in place of braces. This makes it visually harder to parse whitespace and is a potential source of confusion.

![3-5](https://github.com/LilWikipedia/UEFNVersePocketWiki/assets/78571191/7ef50ba4-eae9-47d9-a213-8ba754ad568d)

***
