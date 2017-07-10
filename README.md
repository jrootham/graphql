# graphql
Upgrade GraphQL to allow users to slice data horizontally.

Each row in a data structure is transmitted only if the *select-expr* is true for that row.  No expression defaults to true.

## Syntax
*array-name* *argument-spec* *select-expr* {

*field-name*{*sub-field-name*}}

*argument-spec* ::= *current-spec* | ()

*select-expr* ::= (*boolean-expr*)

*boolean-expr* ::= (*boolean-expr*) | *boolean-field* | *value-test* | exists *sub-array_test* | not *boolean-expr* | and *boolean-list* | or *boolean-list*

*boolean-list* ::= *boolean-expr* | *boolean-expr* *boolean-list*

*value-test* ::= lt *field* *value* | le *field* *value* | eq *field* *value* | ge *field* *value* | gt *field* *value* 

*field* ::= *field-name* | *field-name*.*sub-field-name*

*value* ::= *constant* | *argument*

*sub-array-test* ::= *value-test* where *field* is an array sub field



