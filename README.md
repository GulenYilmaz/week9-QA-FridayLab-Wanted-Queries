# week9-QA-FridayLab-Wanted-Queries
## QA Report

Lots of Manual tests ran a set of the functionality of the app.
The app does not work. 
The "Enter Wanted" function works as intended, with a couple of exceptions:
1. The Driver's License Expired field is supposed to allow for future dates to be entered. It does not allow for any dates beyond the current without showing an error.
2. The same condition is true for the License Plate Expired field.

The major malfunction of the app is that it does not assign or request a Warrant Number when entering a wanted person. Therefore, the Modify and Delete Wanted functions are inaccessible. The Warrant numbers can be spoofed, but the numbers don't correlate to any already existing entry.

| Decision Table       | Case 1 | Case 2 | Case 3 | Case 4 | Case 5 |Case 6| Case 7 | Case 8 | Case 9 | Case 10 | Case 11 | Case 12 |Case 13|Case 14| Case 15 | Case 16 | Case 17 | Case 18|
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|1. Header--> 9-19 char|FALSE|TRUE|
|2. MKE--> Required, 2-4 alpha/special char|FALSE|FALSE|TRUE|
|3. Originating Agency Identifier--> Required, 9 alphanumeric char|FALSE|FALSE|FALSE|TRUE|
|4. Name--> Required, 3-30 char|FALSE|FALSE|FALSE|FALSE|TRUE|
|5. Sex--> Required, 1 character in length, alphabet only, F (female) M (male) and U (unknown) are the only accepted entries|FALSE|FALSE|FALSE|FALSE|FALSE|TRUE|
|6. Race--> Required, 1 character in length, alphabet only|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|TRUE|
|7. Height--> Required, 3 characters in length, numeric only in FII format, where F is feet and I is inches|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|TRUE|
|8. Weight--> Required, 1-3 characters in length, numeric only in lbs, leading zeros to be entered systematically as necessary to change the length to 3 characters in the assembled query.|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|TRUE|
|9. Hair--> Required, 3-10 characters in length, alpha only|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|TRUE|
|10. Offense--> Required, 5-15 characters in length, any allowed|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|TRUE|
|11. Date of Warrant/Violation--> Required, 10 characters in length, numeric in MM/DD/YYYY format (allows dates from 1900 to today +1 day, to account for time zone differences)|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|TRUE|
|12. Drivers License--> Optional, 1-20 characters in length, any characters allowed, if included requires DL State & DL Expiration Year|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|TRUE|
|13. DL State--> Optional, 2 characters in length, State Abbreviations only, if included requires Drivers License & DL Expiration Year|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|TRUE|
|14. DL Expiration Date--> Optional, 10 characters in length, numeric in MM/DD/YYYY format, if included requires Drivers License & DL State, can be future dated.|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|TRUE|
|15. License Plate--> Optional, 5-8 alphanumeric characters in length, if included requires License State & License Year|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|TRUE|
|16. License State--> Optional, 2 characters in length, State Abbreviations only, if included requires License Plate and License Year|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|TRUE|
|17. License Expiration Date--> Optional, 10 characters in length, numeric in MM/DD/YYYY format, if included requires License Plate and License Year, can be future dated.|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|FALSE|TRUE|
