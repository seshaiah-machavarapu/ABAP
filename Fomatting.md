https://help.sap.com/doc/abapdocu_751_index_htm/7.51/en-US/abapcompute_string_format_options.htm

Standard Class: CL_ABAP_FORMAT

```abap
    DATA(lv_var1) = |{ CONV decfloat34( 2345 / 10 ) }|.
    DATA(lv_var2) = |{ CONV decfloat34( 2345 / 10 ) WIDTH = 2 }|.
    DATA(lv_var3) = |{ CONV decfloat34( 2345 / 10 ) WIDTH = 10 ALIGN = RIGHT }|.
    DATA(lv_var4) = |{ CONV decfloat34( 2345 / 10 ) WIDTH = 10 ALIGN = RIGHT PAD = '#' }|.

    DATA(lv_var5) = | { 'Text' CASE = UPPER } |.

    DATA(lv_var6) = | { 1 SIGN = LEFTPLUS } |.

    DATA(lv_var7) = |{ CONV f( 2 / 3 ) }, { CONV f( 2 / 3 ) EXPONENT = -1 }|.


    DATA(lv_var8) = | { -2 / 3 }, {
                     - 2 / 3 DECIMALS = 3 }, {
                     CONV decfloat34( - 2 / 3 ) DECIMALS = 3 }, {
                     CONV f( - 2 / 3 ) DECIMALS = 3 }|.

    " cur in the numeric data types i, p, and f
    " expects a currency ID from the column WAERS of the database table TCURC.
    " Two decimal places are used for every currency ID specified, unless
    " it is contained in the CURRKEY column of the database table TCURX.
    DATA(lv_var9) = |{ 12345678 CURRENCY = 'EUR' }|.

    DATA(lv_var10) = |{ 1000000 NUMBER = ENVIRONMENT }, {
                        1000000 NUMBER = USER }, {
                        1000000 NUMBER = RAW }|.

    DATA(lv_var11) = |{ '1234' ALPHA = IN WIDTH = 10 }|.

    DATA(lv_var12) = |{ '00001234' ALPHA = OUT WIDTH = 10 }|.

    DATA(lv_var13) = |{ sy-datlo DATE = ISO } {
                        sy-datlo DATE = USER } {
                        sy-datlo DATE = ENVIRONMENT }|.

    DATA(lv_var14) = |{ sy-timlo TIME = ISO } {
                        sy-timlo TIME = USER } {
                        sy-timlo TIME = ENVIRONMENT }|.

    GET TIME STAMP FIELD DATA(tmstmp).
    DATA(lv_var15) = |{ tmstmp TIMESTAMP = ISO }|.

    DATA(lv_var16) = |{ tmstmp TIMESTAMP = ISO } {
                        tmstmp TIMESTAMP = ISO TIMEZONE = 'CET'  }|.

    " If cty contains a value from the data base table T005X,
    " the country-specific format defined there is used.
    " If cty is initial, the formatting specified in the user master record is used.
    DATA(lv_var17) = |{ 1000000 COUNTRY = 'DE ' }|.

```
Output:
<img width="320" alt="image" src="https://github.com/user-attachments/assets/17f5ea90-9a06-43e3-8094-c28d63d719dd" />

