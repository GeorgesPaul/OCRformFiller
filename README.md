# OCRformFiller
A formfiller that ignores field names and instead fills forms based on what it sees (like humans do) through OCR/ICR. Would be able to fill website forms as well as PDF and scanned paper forms. 

# The problem with modern webform fillers (Lastpass, Roboform, Keypass, etc)
All web-form fillers (that I've been able to find) rely on correct naming of fields to find fields and fill out forms. The problem with this is that form field names in the majority of online forms are either meaningless, missing, wrong or in the wrong human language. Resulting in form fillers almost never filling out a form completely or correctly. Even the most simple forms are a challenge.

Additionally there's a security risk with this approach when hidden off screen forms are automatically filled with sensitive data without the user's consent. 

# A possible solution
Instead of having the software look at field names in code, have the software look at and analyze the same form that a human sees. Using OCR (optical character recognition) human readable form names can easily be located on a screen and matched to fillable data. Perhaps even when filling out forms in multiple languages (automatic language recognition per field might be possible). 

# This project
Right now this is a place holder to start this project. Very rough very short approach: 

1. Screenshot of form gets send to API
2. API performs OCR on screenshot and detect language. First English, in case that results in bad matches (check with library of words) try other languages that the user configured (language list). Translates to base language (English?) and detects the location of each fillable field. 
3. API sends back list of field x,y location, field size and human readable field name (in original language + translated to English).
4. Consumer of API performs mouse click at each field location and fills out form field by field (no looking into the html/DOM as this would make this approach as useless as the other form fillers). 

# Approach
Create a quick prototype in Python using OpenCV and tesseract and see how well it works on very different looking forms on random websites. If it works better than whatever is the (commercial) market leader, take it to a next level. 

# Advantages: 
* safer: no risk of filling off screen hidden fields 
* actually working: no more useless form fillers that never ever seem to fill out a form completely or correctly 
* works on any form that can be rendered. Not just web pages, but also: word processors, PDFs, scanned documents, accounting software, etc.

# Disadvantage: 
Slower? 
