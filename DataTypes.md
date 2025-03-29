# ABAP Data Types

Refer: https://github.com/SAP-samples/abap-cheat-sheets/blob/main/16_Data_Types_and_Objects.md

## ABAP Built-in Types
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

## Dictionary Data Type
### ABAP Built-in Types and Corresponding Dictionary Data Types

| ABAP Built-in Type | Category                  | Corresponding ABAP Dictionary Data Type | Description |
|--------------------|--------------------------|-----------------------------------------|-------------|
| b                 | Integer                   | INT1                                    | 1-Byte Integer (0 to 255) |
| s                 | Integer                   | INT2                                    | 2-Byte Integer (-32,768 to 32,767) |
| i                 | Integer                   | INT4                                    | 4-Byte Integer (-2,147,483,648 to 2,147,483,647) |
| int8              | Integer                   | INT8                                    | 8-Byte Integer |
| Decfloat16        | Floating Point Number     | DECFLOAT16                              | Floating Point Number (HANA SMALLDECIMAL) |
| Decfloat34        | Floating Point Number     | DECFLOAT34                              | Floating Point Number (HANA DECIMAL) |
| f                 | Binary Floating Point Num | FLTP                                    | Floating Point Number (8 Bytes) |
| p                 | Packed Numbers            | DEC, CURR, QUAN                         | Packed Number in BCD Format |
| c                 | Character-like Type       | CHAR                                    | Character String |
| n                 | Numeric Text Fields       | NUMC                                    | Numerical Text |
| x                 | Byte-like Type            | RAW, LRAW                               | Byte Sequence / Long Byte String |
| d                 | Date and Time Type        | DATS                                    | Date in Format YYYYMMDD |
| t                 | Date and Time Type        | TIMS                                    | Time in Format HHMMSS |
| string            | Text String               | STRING, SSTRING                         | Character String (CLOB) |
| xstring           | Byte String               | RAWSTRING                               | Byte String (BLOB) |

### Additional ABAP Dictionary Types

| ABAP Dictionary Data Type | Short Description                      | ABAP Type |
|---------------------------|----------------------------------------|-----------|
| CUKY                      | Currency Key                           | C(5)      |
| CURR                      | Currency Field in BCD Format          | P((n+1)/2) |
| LANG                      | Language Key                           | C(1)      |
| LCHR                      | Long Character String                  | C(n)      |
| ACCP                      | Posting Period YYYYMM                 | N(6)      |
| CLNT                      | Client                                 | C(3)      |
| DF16_DEC                  | Decimal Floating Point (BCD Format)   | -         |
| DF16_RAW                  | Decimal Floating Point (Binary)       | -         |
| DF16_SCL                  | Decimal Floating Point (Obsolete)     | -         |
| DF34_DEC                  | Decimal Floating Point (BCD Format)   | -         |
| DF34_RAW                  | Decimal Floating Point (Binary)       | -         |
| DF34_SCL                  | Decimal Floating Point (Obsolete)     | -         |
| GEOM_EWKB                 | Geometry (EWKB Representation)        | -         |
| PREC                      | Obsolete Data Type                    | Internal only |


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


Observation 1:

```abap
    DATA number1 TYPE i VALUE -8.
    DATA number2 TYPE i VALUE 3.

    DATA(result) = number1 / number2.
    DATA(output) = |{ number1 } / { number2 } = { result }|. " -8 / 3 = -3

    DATA result1 TYPE p LENGTH 8 DECIMALS 2.
    result1 = number1 / number2.
    DATA(output1) = |{ number1 } / { number2 } = { result1 }|. " -8 / 3 = -2.67
```
Based on receiving type, the result changes.

