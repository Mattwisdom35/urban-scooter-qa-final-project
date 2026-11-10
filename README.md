# Urban Scooter – QA Final Project (Web, Mobile & API)

Manual testing of **Urban Scooter**, a scooter-rental service with a web app, an Android courier app and a REST API backend. Completed as the final project of the TripleTen Quality Assurance program and approved by reviewers.

**85 test cases · 3 platforms · 27 bugs reported in Jira**

## Scope

| Area | What was tested | Test cases | Passed | Failed | Blocked | Bugs |
| --- | --- | --- | --- | --- | --- | --- |
| Web app | "Who the scooter is for" order form: First name, Last name, Address, Subway station, Phone | 51 | 40 | 11 | – | 11 |
| Mobile app | Push notification 2 hours before order deadline; "No Internet connection" pop-up | 26 | 9 | 13 | 4 | 13 |
| Backend API | Create courier (`POST /api/v1/courier`) and delete courier (`DELETE /api/v1/courier/:id`) | 8 | 5 | 3 | – | 3 |

> **Note:** This repository shares a sample of about half of the test cases. The full set is not published, so that the answer key of an active course project stays private. The complete test documentation is available on request.

## Techniques and tools

- **Test design:** equivalence partitioning, boundary value analysis, positive and negative testing, layout checks against Figma designs
- **Web:** cross-browser testing in Google Chrome and Opera at 1280x720
- **Mobile:** Android Studio emulator (API 31), emulator time changes to test time-based notifications, network on/off testing
- **API:** Postman – status codes, response bodies, data checks across endpoints
- **Bug tracking:** Jira (project FPS) – steps to reproduce, expected vs. actual result, severity

## Highlighted bugs

| Area | Bug | Jira |
| --- | --- | --- |
| Mobile | Push notification is not sent 2 hours before the order deadline | FPS-13 |
| Mobile | With no Internet, tapping "Yes" on "Accept the order" shows "Order accepted" instead of the "No Internet connection" pop-up | FPS-33 |
| API | Deleting a courier does not erase the courier's accepted orders (`GET /orders/track` still returns 200) | FPS-30 |
| API | A courier can be created with a non-Latin login ("Иван") – expected 400 Bad Request | FPS-18 |
| Web | Address of exactly 50 characters (valid maximum) is rejected | FPS-34 |
| Web | Phone number of 10 characters (valid minimum) is rejected | FPS-37 |
| Web | Empty Address field is not highlighted and shows no error | FPS-36 |

## Sample files

- [`web-test-cases-sample.csv`](web-test-cases-sample.csv) – 25 of 51 web test cases (First name, Address, Phone), with equivalence classes, boundary values and results for both browsers
- [`mobile-test-cases-sample.csv`](mobile-test-cases-sample.csv) – 13 of 26 Android test cases
- [`api-test-cases-sample.csv`](api-test-cases-sample.csv) – 4 of 8 API test cases (Create courier)

GitHub shows each CSV as a searchable table.

## Author

**Hikmet Osmancik** – Junior QA Engineer
[LinkedIn](https://www.linkedin.com/in/hikmet-osmancik-7938552865665658485/) · [Test automation project](https://github.com/Mattwisdom35/urban-routes-selenium-automation)
