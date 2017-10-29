# ExcelFakeDataDemo

A demonstration spreadsheet with columns creating random and fuzz-type data from standard Excel Functions. Useful to teach and inspire those who want to create random data to use in security fuzzing, exploratory or automated data driven tests and know Excel but aren't confident in their coding abilities.

Please feel free to fork, add your own functions and if you wish raise a pull request to add them to this.

The numerical and date data is not linked to a specific locale, however the companies, city, state and postcode are Australian. I will add more support for other locales as time goes on, however

## Functions (Sheet1)

* Random Numbers - Basic

  * Column A = RAND()

  * Column B = RANDBETWEEN(1000,10000)

* Random Characters - Unicode

  * Column C = CHAR(RANDBETWEEN(1,255))

  * Column D = UNICHAR(RANDBETWEEN(1,65536)) - single 

  * Column E = CHAR(RANDBETWEEN(1,255)) & CHAR(RANDBETWEEN(1,255)) & CHAR(RANDBETWEEN(1,255)) & CHAR(RANDBETWEEN(1,255)) & CHAR(RANDBETWEEN(1,255)) - five ascii characters

  * Column F = UNICHAR(RANDBETWEEN(1,65535)) & UNICHAR(RANDBETWEEN(1,65535)) & UNICHAR(RANDBETWEEN(1,65535)) & UNICHAR(RANDBETWEEN(1,65535)) & UNICHAR(RANDBETWEEN(1,65535)) - five unicode characters

* Random Boolean

  * Column G = IF(RAND() < 0.5, "FALSE", "TRUE") - True or False

* Random non-decimal number systems

  * Column H = DEC2HEX(RANDBETWEEN(0,65535)) - Hexadecimal

  * Column I = DEC2HEX(RANDBETWEEN(0,65535)) - Binary

* Random Fraction

  * Column J = TEXT(RAND(),"# ?/?")

* Random Date between 1/1/1930 and 1/1/2000 (dd/mm/yyyy format - this can be changed easily)

  * Column K = RANDBETWEEN(DATE(1930,1,1),DATE(2000,1,1))

* Random selection from a list in another sheet

  * Australian ASX Companies, sector lookup

    * Column L = INDEX(Sheet2!A:A,RANDBETWEEN(1,2193)) - (See Sheet 2, Column A for reference list)

  * First Name, Last Name, Fake Address line 1 (taken from GenerateData.com)

    * Column M = INDEX(Sheet3!A:A,RANDBETWEEN(2,101)) - First Name (See Sheet 3, Column A for reference list)

    * Column N = INDEX(Sheet3!B:B,RANDBETWEEN(2,101)) - Last Name (See Sheet 3, Column B for reference list)

    * Column O = INDEX(Sheet3!C:C,RANDBETWEEN(2,101)) - Address Line 1 (See Sheet 3, Column C for reference list)

  * City, State, PostCode (Australian Locale)

    * Column P = INDEX(Sheet3!D:D,RANDBETWEEN(2,101)) - City (See Sheet 3, Column D for reference list)

    * Column Q = VLOOKUP(P2,Sheet4!A:B,2) - Finds the state for the corresponding city in column P (See Sheet 4, Column B for reference list)

    * Column R = INDEX(Sheet3!F:F,RANDBETWEEN(2,101))

* Random Phone Number, Random Mobile Number (Australian Locale)
    
  * Column S = "0"&RANDBETWEEN(100000000,999999999) - Random Phone Number
    
  * Column T = "04"&RANDBETWEEN(10000000,99999999) - Random Mobile Number
