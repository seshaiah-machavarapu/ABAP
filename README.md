# ABAP Built-in Types
| Built-in TYpe | Category          |
|---------------|-------------------|
| b             | Integer           |
| s             | Integer           |
| i             | Integer           |
| int8          | Integer           |
| Decfloat16    | Floating Point Number|
| Decfloat34    | Floating Point Number|
| f             | Binary Floating Point Num|
| p             | Packed Number     |
| c             | Character-like    |
| n             | Character-like (Numeric)|
| x             | Byte-like         |
| d             | Date              |
| t             | Time              |
| string        | Text String       |
| xstring       | Byte String       |

Dictionary Data Type
|Data Type	   | Short Description	                                   | Equivalent ABAP Built-In Type |
|-----------   |--------------------------------------                 |-------------------------------|
|CURR	         |Currency Field in BCD Format	                          | P((n+1)/2)                    |
|DEC	         |Packed Number in BCD Format	                          |P((n+1)/2)                     |
|QUAN          |Quantity Field in BCD Format	                          |P((n+1)/2)                     |
|CHAR	         |Character String	                                      |C(n)                           |
|CUKY	         |Currency key for currency fields	                    |C(5)                           |
|LANG	         |Language key	                                         |C(1)                           |
|LCHR	         |Long Character String	                                |C(n)                           |
| UNIT        | Unit key of a quantity field                           | C(n)        |
| INT1        | 1-Byte Integer, 0 to 255                               | Internal only |
| INT2        | 2-byte integer, -32768 to 32767                        | Internal only |
| INT4        | 4-byte integer, -2147483648 to +2147483647             | I            |
| INT8        | 8-Byte Integer                                         |              |
| FLTP        | Floating Point Number                                  | F(8)        |
| NUMC        | Numerical Text                                         | N(n)        |
| LRAW        | Long Byte String                                       | X(n)        |
| RAW         | Byte Sequence                                          | X(n)        |
| RAWSTRING   | Byte String (BLOB)                                     | XSTRING     |
| SSTRING     | Character String                                       |              |
| STRING      | Character String (CLOB)                                | STRING      |
| DATS        | Date in Format YYYYMMDD                                | D           |
| TIMS        | Time in Format HHMMSS                                  | T           |
| DECFLOAT16  | Floating point number (native HANA type SMALLDECIMAL)  |              |
| DECFLOAT34  | Floating point number (native HANA type DECIMAL)       |              |
| DATN        | Date in format YYYYMMDD (native HANA type DATE)        |              |
| TIMN        | Time in format HHMMSS (native HANA type TIME)          |              |
| UTCLONG     | Time stamp (native HANA type TIMESTAMP)                |              |
| ACCP        | Posting Period YYYYMM                                  | N(6)        |
| CLNT        | Client                                                 | C(3)        |
| DF16_DEC    | Decimal floating point number saved in BCD format      |              |
| DF16_RAW    | Decimal floating point number saved as binary number   |              |
| DF16_SCL    | Decimal floating point number with scaling (obsolete)  |              |
| DF34_DEC    | Decimal floating point number saved in BCD format      |              |
| DF34_RAW    | Decimal floating point number saved as binary number   |              |
| DF34_SCL    | Decimal floating point number with scaling (obsolete)  |              |
| GEOM_EWKB   | Geometry (EWKB representation)                         |              |
| PREC        | Obsolete Data Type                                     | Internal only |


- Number Literals are integer numbers with or without sign. Number literals usually have data type I. Only if the value is too large for data type I, type P is used, with a sufficient length and without decimal places.
- Text Literals are character strings in simple quotes. Text literals have type C. The length is derived from the content in quotes. Trailing blanks are ignored.
- String Literals are character strings in a pair of back quotes (`). String literals are of type STRING. They should be used to provide values for string typed data objects.

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

