# Task 1
## Subtask 1
🎯 **8/10** points
## Subtask 2
📁 [Repository](https://github.com/MarekSzmyt/challenge_portfolio_marek) was created
## Subtask 3
👋 Hey! My name is Marek. I started this project to learn basics of manual testing, and hopufully get the deeper understanding of the developement process. I'm already learned a quite a bit of frontend (react ❤️) and I work daily as an UX designer.

Also, testings sounds like a lot of fun - let's try to be a Sherlock Holmes 🕵️! And as a designer I think it would help me to make more User centered products.

*Marek*
## Subtask 4 [WIP]

### The App
Web app for providing a simple documentation about soccer players performance.

### Functionalities
- Login
- Language change (PL/EN)
- Remind Password
- Adding a player
- Editing existing player
- Adding new match
- Editting existing match
- Adding report to the match
- Editting existing report
- Changing display and filters for listings
- Export and print options for listings

#### Ideas/improvements
- there is no way to register new account
- guest login
- option to delete content (player, match, report)
- diplaying yt videos on the website

### User Interface
- Very text heavy makes it hard to comprehend.
- Raw and cold does not make it fun to use.
- A lot of layout missalignements and visual incosistencies makes me feel it's an amateur website.

### User Experience

#### login:
- I would ignore white spaces in the beggining, and at the end when validating the e-mail

#### general:
- adding a player should be available at the players listing
- adding some element (i.e bar) to the selected state on the dashboard, with only color change it may not be accessible
- show password
- incosistent CTA
- dropdown or toggle with all visible states for the language change, current solution is confusing and incosistent with login page
- some limit to the displayed name in tables
[link](https://scouts-test.futbolkolektyw.pl/en/players?lng=en&subpath=en&start=1&_sort=club%3Adesc)
[video](https://drive.google.com/file/d/1AHMjEmylTloeWgw8l6qhxbqOsHPmIT-W/view?usp=share_link)
- headline here could be usefull (i.e. "Social Media Links") to separate this section from the player data 
[link](https://scouts-test.futbolkolektyw.pl/en/players/63c6fb6e4cff3d0bdc152d41/edit)
[screenshot](https://drive.google.com/file/d/1FckhAotyJP56lZiK69UO4X7sMD6mcpDf/view?usp=share_link)
- this div is redundant: `div.MuiPaper-root.MuiCard-root.MuiPaper-elevation1.MuiPaper-rounded`
[screenshot](https://drive.google.com/file/d/1XXIQ4lls4ANVSmY77p10eOPnWVpo-xtU/view?usp=share_link)
- especially on mobile the tables for Reports and Matches should fill the screen width and not be cutted at the conainer
[link](https://scouts-test.futbolkolektyw.pl/en/players/6026b48956c79737b3f3c624/reports)
[screenshot](https://drive.google.com/file/d/1FV01fiXSejGZ0PBRHUTmMhkKdtMy7otz/view?usp=share_link)

#### adding a player:
- asterisk is not explained anywhere
- would not allow adding same language twice
[screenshot](https://drive.google.com/file/d/1WYw1QLn7aPEv4H1yl9CHFANBc_Kz5sGw/view?usp=share_link)
- the tooltip feels disconnected from an input at sumbit validation
[screenshot](https://drive.google.com/file/d/16Qke-lDPNDj33EmGbEtycbxobrGTYxN9/view?usp=share_link)
- much more field validation in general, it's not only makes the UX smoother, and more intuitive but also would reduce potential incosistencies when it comes to providing data and iprove data quality in general (i.e. consisntent phone numbers formating)
- those fields should have pre-defined values similar to the "District" input to allow translation and improve data quality:
  - Level
  - Main Position
  - Second Position

### Defects/Bugs

browser/device:
>Chrome Version 112.0.5615.49 (Official Build) (arm64) | macOS Ventura 13.3.1

#### general:
- client error at remind password page when request is sent
`Payload: user01@getnada.com`
```
{
    "statusCode": 400,
    "error": "Bad Request",
    "message": {
        "code": "EENVELOPE",
        "response": "550 You are not allowed to send e-mails as the domain strapi.io",
        "responseCode": 550,
        "command": "MAIL FROM"
    },
    "data": {
        "code": "EENVELOPE",
        "response": "550 You are not allowed to send e-mails as the domain strapi.io",
        "responseCode": 550,
        "command": "MAIL FROM"
    }
}
```
- item height does not change agter the input validation and the content is clipped
[screenshot](https://drive.google.com/file/d/1E5N0RRIn5uAk1FMyEWeSKltIfdtt2rC_/view?usp=share_link)
- on mobile 2nd link does not work
[video](https://drive.google.com/file/d/1FTmVPSFOrutoswQQB3rpbxnGTKUArZa6/view?usp=share_link)
```
turn null != (a = b({}, n)).start && null != a.limit && (console.warn("Params `start` and `limit` are deprecated. Use `_start` and `_limit`"),
                            a._start = "".concat(n.start * n.limit),
                            a._limit = "".concat(n.limit)),
```
- no field validation when adding a player
- favicon is not loaded: `GET https://scouts-test.futbolkolektyw.pl/pl/favicon.ico 404`
[HAR file](https://drive.google.com/file/d/1xFUkrpT1YLbB3PB-doktXNYxFbwMGnNz/view?usp=share_link)
- "Clear" btn doesn't work when editting existing player
- table download does not translate the information from "Matches" and "Reports"
[CSV file](https://drive.google.com/file/d/1RYMB7UaoNpeNDsOLw9PKNF6eRZ_c-2eW/view?usp=share_link)
- especially on mobile the report page looks just broken
[video](https://drive.google.com/file/d/1oAjPBv0acvlNnHLq2fl8zV-OGw00wJDK/view?usp=share_link)
- validation needed for the age ang height inputs in player page, negative values can be used 
[screenshot](https://drive.google.com/file/d/180gnWX71p1okxy3-Am34YHMGbvjgQkLL/view?usp=share_link)

#### translation:
- "Dev team contact" btn missing polish transaltion
[screenshot](https://drive.google.com/file/d/1IzgpUwrBtnaB2PrmrjlOMdNfnviukMO8/view?usp=share_link)
- "Submit" and "Clear" btn missing polish transaltion
[screenshot](https://drive.google.com/file/d/1OrRa5vpmzpGa2msbT7d_2T5F6YnN1Iow/view?usp=share_link)
- validation hint missing polish transaltion
[screenshot](https://drive.google.com/file/d/1CMmciyi9OAT22FrXr-Utdmh8IKEufyD8/view?usp=share_link)

#### performance:
- long lodaing time for Matches page due to excessive DOM size
[lighthouse report](https://drive.google.com/file/d/1jLWz2neOo_rrcwIFpLVBUfkMr2bnWnfn/view?usp=share_link)
- long lodaing time for Reports page due to excessive DOM size
[lighthouse report](https://drive.google.com/file/d/1GC6bOElM5Kg3QiZXPiNFKz1Pibr2YjFt/view?usp=share_link)

## Subtask 5
Jira Project was created
[backlog](https://markowe.atlassian.net/jira/software/projects/CPP/boards/1/backlog)
