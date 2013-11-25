rentify
=======

Rentify Ebook Page

Online demo at http://antoniopratas.com/rentify


This page was done on top of Skeleton responsive framework (http://www.getskeleton.com/), to allow for usage of the layout grid and responsive layout with pre-made media queries.

The whole purpose was to design a clear and simple layout for this page, with a high focus on image and typography. The images used for rentify were taken from the website (logo and book cover). The colors of the elements (form focus and button) are the same used on the brand. The styles for the button were copied from the original Rentify website (sign up page).

The validation of the form was done in javascript with Parsley.js (http://parsleyjs.org). The verification of the postcode is done with a regex, but to be sure that the postcode is really valid, it should be verified if the postcode introduced exists in a database populated with all the UK postcodes. This could be done via JSON with this API http://www.uk-postcodes.com/api.php

The font used in this page is Open Sans, available and used from the Google Fonts website.

On hovering the book, with flips slightly in 3D, an effect blatantly ripped off from a Codrops tutorial/article at http://tympanus.net/Development/3DBookShowcase/index.html

The site is fully responsive, and to ensure legibility on different sizes, there's an extra background element to cover the photo background and make sure the text is readable.

After the validation of the form, after clicking the "Download ebook" button, jQuery is used to display a hidden div with the message and the link to the download. In a real life case, this wouldn't be safe as a simple inspection of the javascript code would show the link, so the javascript should be encoded and the url should be generated externally for each download, not allowing more than 1 download per url to make sure that these links are not shared.

Regarding verifying the distance between the postcode provided and Rentify's office postcode, I didn't develop this feature. I would do this using Google Maps API Distance Matrix function, as shown here http://maps.googleapis.com/maps/api/distancematrix/json?origins=E16JE+london&destinations="E28DP"+london&sensor=false&units=imperial. After parsing this url in JSON, I would be able to easily detect the distance between these two points. If this distance, in integer, were bigger than 5 (miles), I could show a different message or redirect to a different download page. 

The ruby extra I would do with action-mailer http://guides.rubyonrails.org/action_mailer_basics.html to send an email after validation and sending the data to a database.