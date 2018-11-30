<!-- Answers to the Short Answer Essay Questions go here -->

1. What is the purpose of using _sessions_?
   Sessions allow the server to persist info about the client such as authentification information so that the client's session stays open for a limited amount of time. Improves user experience.

2. What does bcrypt do to help us store passwords in a secure manner.
   Bcrypt is a password hashing function. It uses salted hashing which generates random bytes (the salt) and combines it with the password before hashing thus creating unique hashes across each user’s password. If two users have the same password they will not have the same password hash. This is to prevent rainbow table attacks which can reverse hashed passwords using common hashing functions that do not utilize a salt.

Bcrypt also uses hashing algorithms that are one way functions. They turn any amount of data into a fixed-length “fingerprint” that cannot be reversed. They also have the property that if the input changes by even a tiny bit, the resulting hash is completely different. This is great for protecting passwords, because we want to store passwords in a form that protects them even if the password file itself is compromised, but at the same time, we need to be able to verify that a user’s password is correct.

3. What does bcrypt do to slow down attackers?
   Bcrypt allows us to choose the value of saltRounds, which gives us control over the cost of processing the data. The higher this number is, the longer it takes for the machine to calculate the hash associated with the password. It is important when choosing this value, to select a number high enough that someone who tries to find the password for a user by brute force, requires so much time to generate all the possible hash of passwords that does not compensate him. And on the other hand, it must be small enough so as not to end the user’s patience when registering and logging in (this patience is not usually very high). By default, the saltRounds value is 10.

4. What are the three parts of the JSON Web Token?
   Header, Payload, Signature
