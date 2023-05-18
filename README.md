### Table of contents
1. [**Exploration Testing**](#task-1---exploration-testing)
    - [Prework](#subtask-1---prework)
    - [Project Setup](#subtask-2---project-setup)
    - [Introduction](#subtask-3---introduction)
    - [Exploration Testing](#subtask-4---exploration-testing)
    - [Jira Setup](#subtask-5---jira-setup)
2. [**Test Cases**](#task-2---test-cases)
    - [User Story](#subtask-1---user-story)
    - [Experience](#subtask-2---experience)
    - [Writing Test Cases](#subtask-3---writing-test-cases)
    - [Mobile App](#subtask-4---mobile-app)
3. [**Bug Reporting**](#task-3---bug-reporting)
    - [Template](#subtask-1---template)
    - [Bug Reporting](#subtask-2---bug-reporting)
    - [Report](#subtask-3---report)
    - [Tour](#subtask-4---tour)
4. [**Mobile App Testing**](#task-4---mobile-app-testing)
    - [Template](#subtask-1---template-1)
    - [Testing](#subtask-2---testing)
    - [Findings](#subtask-3---findings)
    - [Natvie vs Web](#subtask-4---natvie-vs-web)
5. [**SQL**](#task-5---sql)
    - [Basics](#subtask-1---basics)
    - [Environment Setup](#subtask-2---environment-setup)
    - [Exercises](#subtask-3---exercises)

# [Task 1](https://drive.google.com/drive/folders/1Q-jXEWLslwTm31_AOYpP8yzxxwIziWEm?usp=share_link) - Exploration Testing
![Person holding giant magnifying glass in front of a laptop.](/assets/images/task01.jpg)

## Subtask 1 - Prework
🎯 **8/10** points

## Subtask 2 - Project Setup
📁 [Repository](https://github.com/MarekSzmyt/challenge_portfolio_marek) was created

## Subtask 3 - Introduction
👋 Hey! My name is Marek. I started this project to learn basics of manual testing, and hopufully get the deeper understanding of the developement process. I already learned a quite a bit of frontend (react ❤️) and I work daily as an UX designer.

Testings sounds like a lot of fun - let's try to be the Sherlock Holmes 🕵️! Also, since I'm a designer I think it would help me to make more User centered products.

*Marek*

## Subtask 4 - Exploration Testing

### The App
Web app for providing a simple documentation about soccer players performance. Allows to create player profiles, add mathces their participated in, and gather reports aboutt their performance.

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
- uploading player photos

### User Interface

>Personally I don't especially like it. It makes the process of adding data very boring, and it's not rewarding at all with all of the overwhelming text.

- Very text heavy makes it hard to comprehend.
- Raw and cold does not make it fun to use.
- A lot of layout missalignements and visual incosistencies makes it sometimes confusing.

### User Experience

>Overall I had no problems when adding players, althought the initial feeling is a bit overwhelming. The deeper I go (matches → reports) the less understandable the process becomes. Especially reports are confusing for me, the flow is much more different there than the player and match addition.

#### general:
- adding a player should be available at the players listing
- adding some element (i.e bar) to the selected state on the dashboard, with only color change it may not be accessible
- show password option
- incosistent CTA, both wording and styling
- dropdown or toggle with all visible states for the language change, current solution is confusing and incosistent with login page
- some limit to the displayed name in tables →
[link](https://scouts-test.futbolkolektyw.pl/en/players?lng=en&subpath=en&start=1&_sort=club%3Adesc) |
[video](https://drive.google.com/file/d/1AHMjEmylTloeWgw8l6qhxbqOsHPmIT-W/view?usp=share_link)
- headline on **Add player** page could be usefull (i.e. "Social Media Links") to separate sections from each other →
[link](https://scouts-test.futbolkolektyw.pl/en/players/63c6fb6e4cff3d0bdc152d41/edit) |
[screenshot](https://drive.google.com/file/d/1FckhAotyJP56lZiK69UO4X7sMD6mcpDf/view?usp=share_link)
- this div feels redundant here: `div.MuiPaper-root.MuiCard-root.MuiPaper-elevation1.MuiPaper-rounded` →
[screenshot](https://drive.google.com/file/d/1XXIQ4lls4ANVSmY77p10eOPnWVpo-xtU/view?usp=share_link)
- especially on mobile the tables for **Reports** and **Matches** should fill the screen width and not be cutted at the conainer →
[link](https://scouts-test.futbolkolektyw.pl/en/players/6026b48956c79737b3f3c624/reports) |
[screenshot](https://drive.google.com/file/d/1FV01fiXSejGZ0PBRHUTmMhkKdtMy7otz/view?usp=share_link)
- cards on the **Main page** on lager mobile screens ([screenshot](https://drive.google.com/file/d/1tVBUUREy0GClkdC6LWbVZoQNhcfIrIAr/view?usp=share_link) example for Samsung Galaxy S20 Ultra) should fill the device witdth, instead they are capped at 345px:
```css
.jss139 {
    max-width: 345px;
}
```
- contrast for this element is very low `div.ReportFooterStyled-x8k29a-0.kqrEhp` →
[screenshot](https://drive.google.com/file/d/1LU-vW2f4ys4GRzIGpouwCGbZjQzJdxRW/view?usp=share_link)

#### login:
- I would ignore white spaces in the beggining, and at the end when validating the e-mail

#### adding a player:
- asterisk is not explained anywhere *(very minor issue)*
- the tooltip feels disconnected from an input at sumbit validation →
[screenshot](https://drive.google.com/file/d/16Qke-lDPNDj33EmGbEtycbxobrGTYxN9/view?usp=share_link)
- much more field validation in general, it's not only makes the UX smoother, and more intuitive but also would reduce potential incosistencies when it comes to providing data and improve data quality in general:
  - would not allow adding same language twice →
  [screenshot](https://drive.google.com/file/d/1WYw1QLn7aPEv4H1yl9CHFANBc_Kz5sGw/view?usp=share_link)
  - at least simple verification, hint with the formatting and/or limitting the lenght
  - **weight** and **height** inputs should be numbers only (you can type "e" letter), validation is present but we could avoid typos just by changing     the field type
  - e-mail format check
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
```js
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
- item height does not change after the input validation and the content is clipped →
[screenshot](https://drive.google.com/file/d/1E5N0RRIn5uAk1FMyEWeSKltIfdtt2rC_/view?usp=share_link)
- on mobile 2nd link takes very long time to work →
[video](https://drive.google.com/file/d/1FTmVPSFOrutoswQQB3rpbxnGTKUArZa6/view?usp=share_link)
```js
turn null != (a = b({}, n)).start && null != a.limit && (console.warn("Params `start` and `limit` are deprecated. Use `_start` and `_limit`"),
                            a._start = "".concat(n.start * n.limit),
                            a._limit = "".concat(n.limit)),
```
- favicon is not loaded: `GET https://scouts-test.futbolkolektyw.pl/pl/favicon.ico 404` →
[HAR file](https://drive.google.com/file/d/1xFUkrpT1YLbB3PB-doktXNYxFbwMGnNz/view?usp=share_link)
- "Clear" btn doesn't work when editting existing player
- table download does not translate the information from **Matches** and **Reports** →
[CSV file](https://drive.google.com/file/d/1RYMB7UaoNpeNDsOLw9PKNF6eRZ_c-2eW/view?usp=share_link)
- especially on mobile the report page looks just broken →
[video](https://drive.google.com/file/d/1oAjPBv0acvlNnHLq2fl8zV-OGw00wJDK/view?usp=share_link)
- validation needed for the **weight** and **height** inputs in player page, negative values can be used  →
[screenshot](https://drive.google.com/file/d/180gnWX71p1okxy3-Am34YHMGbvjgQkLL/view?usp=share_link)
- `Incompatible href and as values` when clicking "back to report" btn on the "unsaved report" card
```js
42032078bbadf019700308e0ffe503d5056449.e5058d62b3c6fbb81936.js:1 Uncaught (in promise) Error: The provided `as` value (/en/players/630a542662fd50f9620fda33/reports/start) is incompatible with the `href` value (/players/[id]/reports/start). Read more: https://err.sh/vercel/next.js/incompatible-href-as
    at t.<anonymous> (f542032078bbadf019700308e0ffe503d5056449.e5058d62b3c6fbb81936.js:1:19629)
    at c (f542032078bbadf019700308e0ffe503d5056449.e5058d62b3c6fbb81936.js:1:2099)
    at Generator._invoke (f542032078bbadf019700308e0ffe503d5056449.e5058d62b3c6fbb81936.js:1:1852)
    at Generator.next (f542032078bbadf019700308e0ffe503d5056449.e5058d62b3c6fbb81936.js:1:2458)
    at r (f542032078bbadf019700308e0ffe503d5056449.e5058d62b3c6fbb81936.js:1:7451)
    at u (f542032078bbadf019700308e0ffe503d5056449.e5058d62b3c6fbb81936.js:1:7662)
(
```
- Logo is slightly too small to be sharp on the more pixel dense screens →
[link](https://scouts-test.futbolkolektyw.pl/static/images/logo_platforma.png)

#### translation:
- "Dev team contact" btn missing polish transaltion →
[screenshot](https://drive.google.com/file/d/1IzgpUwrBtnaB2PrmrjlOMdNfnviukMO8/view?usp=share_link)
- "Submit" and "Clear" btn missing polish transaltion →
[screenshot](https://drive.google.com/file/d/1OrRa5vpmzpGa2msbT7d_2T5F6YnN1Iow/view?usp=share_link)
- validation hint missing polish transaltion →
[screenshot](https://drive.google.com/file/d/1CMmciyi9OAT22FrXr-Utdmh8IKEufyD8/view?usp=share_link)
- hints on hover for icons in the **Players** page missing polish transaltion →
[screenshot](https://drive.google.com/file/d/1SjsT4ITSQQ93NH92b277vhZO_F-O8OSV/view?usp=sharing)

#### performance:

- font blocking the page load is pretty bad →
[screenshot](https://drive.google.com/file/d/1KT0X7osSIrb_tliPFuGVVg4WlmSfSQYC/view?usp=share_link)
- long loading time for Matches page due to excessive DOM size →
[lighthouse report](https://drive.google.com/file/d/1jLWz2neOo_rrcwIFpLVBUfkMr2bnWnfn/view?usp=share_link)
- long loading time for Reports page due to excessive DOM size →
[lighthouse report](https://drive.google.com/file/d/1GC6bOElM5Kg3QiZXPiNFKz1Pibr2YjFt/view?usp=share_link)

## Subtask 5 - Jira Setup
Jira Project was created →
[backlog](https://markowe.atlassian.net/jira/software/projects/CPP/boards/1/backlog)

# [Task 2](https://drive.google.com/drive/folders/1fSPjXY9pEjqSDY5uHGb0hraGFfBgV4I-?usp=share_link) - Test Cases
![Two people making a notes on a giant board.](/assets/images/task02.jpg)

## Subtask 1 - User Story
Test cases based on User Story

✏️ [doc](https://docs.google.com/document/d/1K0aCeP-jnbxXgN03Nj1GbVopt8PWaABVdFBMJwbmjPg/edit?usp=share_link)

## Subtask 2 - Experience
Test cases based on own experience

✏️ [doc](https://docs.google.com/document/d/18663j-9_0rqHyhF0ruEKW5b0tO1VjSe05aGh7vr4qXY/edit?usp=share_link)

## Subtask 3 - Writing Test Cases
> Why do we write test cases?

Test cases help to verify whether the application or just a feature satisfies the requirements, and is free of defects. Without them some things can be overlooked or missed, and the quality of the final product can be harmed. In worst case scenario some bugs may cause big finicial costs so making sure that tet cases cover all crucial point it's very importatnt.

It is also a handy cooperation tool so the work can be easly followed by other tersters, and shared with others (devs, pm, client etc.)

## Subtask 4 - Mobile App
Test cases for an Mobile app →
[link](https://pickeatup.io/)

✅ [jira task](https://markowe.atlassian.net/browse/CPP-1?atlOrigin=eyJpIjoiYjQ5ZThjZWZhZGJhNGIzODk3YmFkZGZkNGYxY2QzZDQiLCJwIjoiaiJ9)

✏️ [doc](https://docs.google.com/document/d/1grzubanxI90KDDDgP6iut79SIRfEz_UBv7Q1vsEYIsY/edit?usp=share_link)

# [Task 3](https://drive.google.com/drive/folders/1HbbcxWWACGM2Ihk50s17DpDg39vFfVN3?usp=sharing) - Bug Reporting
![Person holding giant magnifying glass in front of a laptop with a bug inside of it.](/assets/images/task03.jpg)

## Subtask 1 - Template
Bug reporting template

✏️ [doc](https://docs.google.com/document/d/18Fc9Mmw7BVw2PmVM2gNdmzkdrAXCq829Q3xBa8sLB7k/edit?usp=sharing)

## Subtask 2 - Bug Reporting
Bug reporting based on the Test Cases

✏️ [Test Cases](https://docs.google.com/document/d/1UFOdOIuCxAj-YNvehxKNawdWyxfMCO9-I0A9pZeTxfw/edit?usp=sharing) | 
[Bug Reports](https://docs.google.com/document/d/15Mj7BSwYYjIpi1GvPfLHnKzI-z15UBQHYx3gEx1i3EQ/edit?usp=sharing)

## Subtask 3 - Report

📊 [sheet](https://docs.google.com/spreadsheets/d/1iiE9J9AH0uCzbSfIuPodX0WcmWq8aLDkDDmnVszWsa8/edit?usp=sharing)

![Testing raport with charts.](/assets/images/report.png)

## Subtask 4 - Tour
👻 Anti social Tour

✏️ [doc](https://docs.google.com/document/d/1nbsffiirVOL1N7PLJNBVvycFOdIRlQrGwC8euJx0lds/edit?usp=sharing)

# [Task 4](https://drive.google.com/drive/folders/1GgWi2NbGUnkjwqOgI94zNyxtdoGV6mYE?usp=share_link) - Mobile App Testing
![Person in fron of giant mobile device.](/assets/images/task04.jpg)

## Subtask 1 - Template
Bug reporting template

✏️ [doc](https://docs.google.com/document/d/1hHxfr0lF5UeJCMjAvIfl1IE_0wJH_sECKeyu-1Em-b4/edit?usp=share_link)

## Subtask 2 - Testing
Exploration Testing & Bug Reporting

✏️ [doc](https://docs.google.com/document/d/1HKlwypUkiFY4RdIiLoQ2dvxXfgyWlWTDc2707NsmrsQ/edit?usp=share_link)

## Subtask 3 - Findings

>What is this app for? What is the purpose of this app?

It's a digital marketplace for a wide range of products and services. It makes money through fees and subscriptions, and monetizes traffic with ads.

• • •

>Who is going to be the end user of the application?

A private or business entity who wants to exchange products or services.

• • •

>Do you think the application is user friendly?

For me, a user-friendly app is intuitive and understandable for any user.

OLX follows those principles when making their app very easy to use. I like how it is structured and organized, and it's easy to find the information or options you're looking for. Also, it is aesthetically pleasing and visually appealing. It doesn't try to overwhelm you with colors and let you focus on content.

• • •

>How would you improve the application? What would you improve about it? Do you have any idea for additional functionality?

- Compare offers functionality
- Offer bundling
- Suggesting category when adding a product
- Creating specific product pages with:
    - Prices history
    - Transaction history
    - Product reviews

• • •

>What differences do you see between testing a web application and a native one?

**Focusing on different navigation 👆 🤌**

Tapping, swiping, pulling, and pinching, as well as voice assistants and commands.

• • •

**Offline is a thing 🛜 ✈️**

While web apps require a connection to be used, some mobile apps can be used offline.

• • •

**It's not a browser 🖥️ ❌**

Since it is not using a browser, there are a bunch of new questions that need to be addressed:
- How much battery life does it drain?
- How much memory does it use?
- Can you install and uninstall it?

## Subtask 4 - Natvie vs Web 
Testing Native & Web App →
[link](https://swipeto.pl/)

✅ [template](https://markowe.atlassian.net/browse/CPP-9?atlOrigin=eyJpIjoiODNmMWM2MGNmYWRmNDg1MjlkZTY2MTU2YTY5MTJmMWYiLCJwIjoiaiJ9)

🔴 NATIVE: [CPP-10](https://markowe.atlassian.net/browse/CPP-10) | 
[CPP-11](https://markowe.atlassian.net/browse/CPP-11) |
[CPP-12](https://markowe.atlassian.net/browse/CPP-12) | 
[CPP-13](https://markowe.atlassian.net/browse/CPP-13) | 
[CPP-14](https://markowe.atlassian.net/browse/CPP-14)

🔴 WEB: [CPP-15](https://markowe.atlassian.net/browse/CPP-15) | 
[CPP-16](https://markowe.atlassian.net/browse/CPP-16) |
[CPP-17](https://markowe.atlassian.net/browse/CPP-17) | 
[CPP-18](https://markowe.atlassian.net/browse/CPP-18) | 
[CPP-19](https://markowe.atlassian.net/browse/CPP-19)

# Task 5 - SQL
![Person touching giant code blocks.](/assets/images/task05.jpg)

## Subtask 1 - Basics


<img align="right" src="/assets/images/sqlTest.png" alt="Test result confirmation." width="460" height="240">

[🎓 Tutorial link:](https://www.w3schools.com/sql/exercise.asp?)

`Select`, `Where`, `Order By`, `Insert`, `Null`, `Update`, `Delete`, `Functions`, `Like`, `Wildcards`, `In`, `Between`, `Alias`, `Join`, `Group By`, `Database`
<br clear="right"/>

## Subtask 2 - Environment Setup
Setup the server and import the database using xampp.

📊 [database](https://drive.google.com/file/d/11ToeE1M3G6Ea1eiV40dxNcuqG_Ew3H0k/view?usp=share_link)

## Subtask 3 - Exercises

>1. Display the **actors** table in alphabetical order by sorting by the **surname** column.

<img align="right" src="/assets/images/sql01.png" alt="screenshot with sorted table" width="242" height="250">

```sql
SELECT * FROM Customers
ORDER BY surname;
```

<br clear="right"/>

• • •

>2. Display a **movie** that was made in **2019**.

<img align="right" src="/assets/images/sql02.png" alt="screenshot with sorted table" width="313" height="50">

```sql
SELECT * FROM movies
WHERE year_of_production = '2019';
```

<br clear="right"/>

• • •

>3. Display all **movies** made between **1900** and **1999**.

<img align="right" src="/assets/images/sql03.png" alt="screenshot with sorted table" width="481" height="92">

```sql
SELECT * FROM movies
WHERE year_of_production BETWEEN 1900 AND 1999;
```

<br clear="right"/>

• • •

>4. Display ONLY the **title** and **price** of **movies** that cost less than **$7**

<img align="right" src="/assets/images/sql04.png" alt="screenshot with sorted table" width="282" height="139">

```sql
SELECT title, price FROM movies
WHERE price < 7;
```

<br clear="right"/>

• • •

>5. Use the logical `AND` operator to display **actors** with **actor_ids** between **4-7** (4 and 7 included). Don't use `BETWEEN` operator.

<img align="right" src="/assets/images/sql05.png" alt="screenshot with sorted table" width="227" height="118">

```sql
SELECT * FROM actors
WHERE actor_id >= 4
AND actor_id <= 7;
```

<br clear="right"/>

• • •

>6. Display **customers** with **customer_id 2,4,6** use logical condition for this.

<img align="right" src="/assets/images/sql06.png" alt="screenshot with sorted table" width="342" height="94">

```sql
SELECT * FROM customers
WHERE customer_id = '2'
OR customer_id = '4'
OR customer_id = '6';
```

<br clear="right"/>

• • •

>7. Display **customers** with **customer_id 1,3,5** use `IN` operator for this.

<img align="right" src="/assets/images/sql07.png" alt="screenshot with sorted table" width="330" height="96">

```sql
SELECT * FROM customers
WHERE customer_id IN (1, 3, 5);
```

<br clear="right"/>

• • •

>8. Display the details of all people in the **actors** table whose name starts with **'An'**.

<img align="right" src="/assets/images/sql08.png" alt="screenshot with sorted table" width="204" height="73">

```sql
SELECT * FROM actors
WHERE name LIKE 'An%';
```

<br clear="right"/>

• • •

>9. Display details of a **customer** who does not have an **email address** provided.

<img align="right" src="/assets/images/sql09.png" alt="screenshot with sorted table" width="281" height="49">

```sql
SELECT * FROM customers
WHERE email IS NULL;
```

<br clear="right"/>

• • •

>10. Display all **movies** priced over **$9** and with an **movie_id** between **2 and 8**.

<img align="right" src="/assets/images/sql10.png" alt="screenshot with sorted table" width="349" height="95">

```sql
SELECT * FROM movies
WHERE price > 9
AND movie_id BETWEEN 2 AND 8;
```

<br clear="right"/>
