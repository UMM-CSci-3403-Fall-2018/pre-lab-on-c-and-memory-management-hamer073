# Leak report
Strip Calloc Memory Leak
* The function strip() allocates memory for a string result, which it then returns so strip() cannot free that memory
* Instead the memory has to be freed in the is_clean() function.
* strip() however has a special case where if the string is all spaces, it just returns the empty string as a static pointer which we can't free.
* So we have to check first if the string is empty before freeing the memory. If it is then we just return the result and let the system take care of it. 

_Use this document to describe whatever memory leaks you find in `clean_whitespace.c` and how you might fix them. You should also probably remove this explanatory text._

