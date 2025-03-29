# ABAP
Built-in Types

   " Is this Okay to use single quote instead of back quote for a string?
   DATA lv_str1 TYPE string VALUE 'This is a string'.
   DATA lv_str2 TYPE string VALUE `This is also a string`.
   out->write( lv_str1 ).
   out->write( lv_str2 ).

   DATA(lv_str3) = 'Is this a string?'.
   DATA(lv_str4) = `Is this a string?`.
   out->write( lv_str3 ).
   out->write( lv_str4 ).

   <img width="340" alt="ABAP Strings" src="https://github.com/user-attachments/assets/c8f5c376-1010-4938-b355-90c958ac1b2c" />

When a string is placed in single quotes, it is considered as character literals. In the case of lv_str1, auto-conversion happened from character literals to string.
