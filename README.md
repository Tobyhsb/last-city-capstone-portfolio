# Last City - IT 485 Team Capstone

**Application troubleshooting, cloud integration, testing, and technical documentation**

Last City is a browser-based city-building and incremental strategy game created by **CTRL + ALT + DEFEAT**. This repository documents my contributions and the support-related skills I developed through the project. The original application remains in the team's repository.

[Original team repository](https://github.com/CTRL-ALT-DEFEAT-LAST-CITY/ctrl-alt-defeat-last-city) | [Public game](https://ctrl-alt-defeat-last-city.github.io/ctrl-alt-defeat-last-city/) | [My profile](https://github.com/Tobyhsb)

## Project overview

The team application combines resource gathering, buildings, upgrades, and progression across five zones. It includes browser local saves, Supabase authentication and cloud saves, and account-specific save ownership checks.

**Technologies:** JavaScript, HTML, CSS, localStorage, Supabase, PostgreSQL/SQL, Google OAuth, Git, GitHub, and GitHub Pages.

## My contributions

- Worked on JavaScript gameplay and HTML/CSS interface updates, including navigation, player guidance, and action feedback.
- Contributed to account and cloud-save integration, account-specific storage, synchronization, and conflict handling.
- Troubleshot connection and account-service failures, improved validation and error feedback, and preserved browser progress during failures.
- Contributed regression coverage for save conflicts, account isolation, unavailable services, and recovery behavior.
- Supported repository organization, GitHub Pages deployment, setup and troubleshooting documentation, feature planning, and coordination of team testing.

## Technical case studies

### Save conflicts and database retries

**Problem:** An earlier application save-conflict response used SQLSTATE `40001`, which could trigger repeated database retries.

**Work:** Updated the SQL response to `PT409`, aligned client conflict handling, and added regression checks. The repair retained account ownership checks and revision-based save protection.

**Result:** The implementation provides an explicit conflict-resolution path instead of treating the conflict as a retryable database transaction failure.

**Repository evidence:** [SQL repair](https://github.com/CTRL-ALT-DEFEAT-LAST-CITY/ctrl-alt-defeat-last-city/commit/0352f8f5afb20ffef76ff55d2ff99c3c3a68abf2), [client handling](https://github.com/CTRL-ALT-DEFEAT-LAST-CITY/ctrl-alt-defeat-last-city/commit/feae3f3198f9e8f352cb91f38d45e45d2f578e4e).

### Keeping progress safe when account services fail

**Problem:** Connection failures needed to leave account controls usable and retain the player's browser progress.

**Work:** Investigated API responses and configuration, added clearer failure messages and request handling, and tested unavailable Google preflight and email-login connections.

**Result:** The tested failure paths restore usable account controls and keep browser progress available.

**Repository evidence:** [Outage regression coverage](https://github.com/CTRL-ALT-DEFEAT-LAST-CITY/ctrl-alt-defeat-last-city/commit/cf256fc06f7603740794456ec70e9a6d7b235b74), [replacement cloud configuration](https://github.com/CTRL-ALT-DEFEAT-LAST-CITY/ctrl-alt-defeat-last-city/commit/109aba422fa3e313566cfb7a80bef2a8e7da52aa).

### Making the application easier to maintain

**Work:** Helped separate gameplay, interface, cloud integration, and styling files by responsibility. Documented setup and troubleshooting procedures, supported publication checks, and asked teammates to report bugs with screenshots and reproduction steps.

**Repository evidence:** [Organized runtime update](https://github.com/CTRL-ALT-DEFEAT-LAST-CITY/ctrl-alt-defeat-last-city/commit/ec34bbbf05b8c40565e6f9ae0ffcf1f09fc3fe49).

## Relevance to IT support

This project developed my experience reproducing failures, separating application behavior from service availability, reviewing account permissions, preserving data during recovery, testing fixes, and communicating technical steps.

## Teamwork and development approach

This was a collaborative, AI-assisted project. I directed feature requirements and worked through integration, troubleshooting, testing, documentation, and deployment with AI tools and teammates. I do not claim sole authorship of the application or every line of code.

Commit records identify published changes but do not capture every contributor's work. The linked examples show changes recorded under my `IT_potato` / `Tobyhsb` identity; other substantial updates are attributed to teammates. My latest local interface redesign is work in progress and may differ from the public game.

The case studies describe implemented changes and recorded verification, rather than a guarantee of current service availability.
