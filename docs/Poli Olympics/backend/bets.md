---
sidebar_position: 3
---

# Bets

In betsApp, PoliOlympics have the competionId = 13, and each sport have an assigned sportId:

- "Fotbal" : 4,
- "Handbal" : 5,
- "Volei" : 6,
- "StreetBall" : 7,
- "Tenis de picior" : 8,
- "Tenis de masa" : 9

The same way, each faculty has an unique Id.

### **Bets request**
1. BetMatch
``` javascript
axios.post(
    constants.BETSURL + '/bets',
    {
        "amount": Number.parseInt(bet.amount),
        "matchId": match.betsid,
        "mutexScenarioId": bet.scenario,
        "scoreBets": bet.scores
    },
    {
        "headers": {
            "poli_key": constants.poli_key,
            "Authorization": email
        }
    }
```

2. GetHistory
``` javascript
axios.get(
constants.BETSURL + '/bets/history',
{
    "headers": {
        "poli_key": constants.poli_key,
        "Authorization": email,
    }
}
)
```

3. GetLeaderboard
``` javascript
axios.get(
constants.BETSURL + '/competitions/13/leaderboard',
{
    "headers": {
        "poli_key": constants.poli_key,
        "Authorization": email,
    }
}
)
```

4. GetMatch
``` javascript
axios.get(
constants.BETSURL + '/competitions/13/matches/' + match.betsid + '/forBetting',
{
    "headers": {
        "poli_key": constants.poli_key,
        "Authorization": email,
    }
}
)
```

5. GetData
``` javascript
axios.get(
constants.BETSURL + '/competitions/13/matches/62/forBetting',
{
    "headers": {
        "poli_key": constants.poli_key,
        "Authorization": email,
    }
}
)
// Used in getWallet => .then(res.send("amount": data["better"]["wallet"]))
```
6. DeleteBet
``` javascript
axios.delete(
constants.BETSURL + '/bets/' + betId,
{
    "headers": {
        "poli_key": constants.poli_key,
        "Authorization": email
    }
}
)
```
7. SaveMatch - used to create a match
``` javascript
axios.post(
constants.BETSURL + '/competitions/13/matches',
{
    "sportId": constants.SPORT_BETSID[sportType],
    "teamIds": [
        constants.FAC_BETSID[team1],
        constants.FAC_BETSID[team2]
    ],
    "competitionId": constants.POLI_BETSID,
},
{
    "headers": {
        "Authorization": 'Bearer ' + constants.BETSJWT
    }
}
)