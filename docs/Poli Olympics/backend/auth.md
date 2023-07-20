---
sidebar_position: 2
---

# Auth

All authorization and authentication logic is done using JWT.

User creation logic:

1. When a user register, his info in saved in as RegisterInfo and saved in register table with a token. At this point, we also send a request to betsApp to accept this email as a better in our competition. Now, we send an email with a link to '/confirm/${token}' to confirm the account.

2. When a user confirm their account, then is deleted from register table and a User is created and put into the users table.

User roles:

1. Manager - Can change the role of other users.
2. Admin - Can add matches and change scores.
3. Participant.