---
sidebar_position: 4
---

# Most complex componets

## Login/Register

In index.js, for the route "/login" we render our Register component with *Login component as a prop* (similar for resetPassword and forgotPassword routes). We use *Input componet* to handle our inputs and our general validator to validate the form data before send it to backend.

## Bets Dashboard

Contains information about your wallet, your betting history and the dashboard with the top 14 betters and their tokens. To get all this information, we need to make 3 separate requests to betsApp (made through our request service). Here we use as helpers *BetCard* and *BetterRow*

## Games

Separated links for every sport -> "/games/${sport}".
Each page contains links to bracket, rules and betting guide, besides all the matches of that sport.

The matches are separated in 3 categories: **Live**, **Upcoming** and **Results**. Partipants can bet only on upcoming matches.

In this component we make 3 request to betsApp:

- getWallet, to check that a user only makes bets only with his available tokens
- getBetterHistory, to check if a user already made a bet on a match
- getSpecificMatches, to get all matches from that sport

In this component is where our frontend uses websockets to have access to live score (more details on Websockets Section). 

Games uses *GameRow component*, where the actual bet can be made for upcoming matches (after completing the modal form, a request is send to betsApp).
