# ABAP
Built-in Types

- Number Literals are integer numbers with or without sign. Number literals usually have data type I. Only if the value is too large for data type I, type P is used, with a sufficient length and without decimal places.
- Text Literals are character strings in simple quotes. Text literals have type C. The length is derived from the content in quotes. Trailing blanks are ignored.
- String Literals are character strings in a pair of back quotes (`). String literals are of type STRING. They should be used to provide values for string typed data objects.
- 
```abap
   " Is this Okay to use single quote instead of back quote for a string?
   DATA lv_str1 TYPE string VALUE 'This is a string'.
   DATA lv_str2 TYPE string VALUE `This is also a string`.
   out->write( lv_str1 ).
   out->write( lv_str2 ).

   DATA(lv_str3) = 'Is this a string?'.
   DATA(lv_str4) = `Is this a string?`.
   out->write( lv_str3 ).
   out->write( lv_str4 ).
```

<img width="340" alt="ABAP Strings" src="https://github.com/user-attachments/assets/c8f5c376-1010-4938-b355-90c958ac1b2c" />

When a string is placed in single quotes, it is considered as character literals. In the case of lv_str1, auto-conversion happened from character literals to string.

The following image shows some more examples of implicit type conversions.

![image](https://github.com/user-attachments/assets/db5fdbd1-5277-4852-949b-5b091066300f)

