# Dry Principle
It means don't repeat yourself. In coding, there is no duplicate rules and logic can be exist only in one place.
DRY helps to reduce bugs, maintain code and improve security.

However, in this juice-shop challenge "Repeat Registration", I tried to register as a new customer.
I typed the 1st password and repeat it correctly, then will change the original password to a new password.
And I tried to register and it succeed. This shows validation logic is duplicated.

# Empty User Registration
I used burp suite and register a new account by turning on the proxy. Then after entering the email and password those, I found the post and send to repeater and click send. Then turn off proxy and delete the email and password into "". Then, click send again and empty registration challenge is done.
