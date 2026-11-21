# Wordstellar

**Illuminate your lexicon.**

Wordstellar is a daily synonym game set beneath a sky of stars. You get five words, one at a time, with 30 seconds to find as many synonyms as you can. Every accepted answer lights a star. Less familiar synonyms earn more points, and your final score reveals a constellation.

You don’t need to be a word expert. Each word comes with a definition and an example sentence to get you started.

**[Play Wordstellar](https://wordstellar-application.vercel.app/)** · **[Read the user guide](USER_GUIDE.md)**

## How it works

1. Start the daily challenge using the telescope on the home screen.
2. Type a synonym and press Enter, or select Add.
3. Keep finding words until the 30 seconds are up.
4. Read the word’s origin and see other possible answers before starting the next round.
5. Finish all five rounds to discover your constellation and share your score.

Everyone gets the same daily challenge. From 21 November 2026, all five words are familiar, with no harder final round. Older dated challenges keep their original words. The next challenge arrives at midnight UTC.

## Points and stars

| Answer category | Points |
| --- | --- |
| Common | 1 |
| Uncommon | 2 |
| Rare | 3 |

Each accepted answer lights one star, regardless of its points. Repeated answers and listed spelling variants count once. Wrong answers do not lose points.

Categories use word frequency as a guide to familiarity. A longer word is not automatically worth more. Answers are checked against reviewed lists for the meaning shown, so some valid synonyms may still be missing.

## Find your constellation

| Total points | Constellation |
| --- | --- |
| 0–3 | Delphinus |
| 4–7 | Lyra |
| 8–11 | Aquila |
| 12–19 | Cygnus |
| 20+ | Orion |

Orion starts at 20 points. Previous results use these bands too, with points and streaks preserved. The bands represent progress in the game, rather than the brightness of real constellations.

## Your Universe

You can play without an account. Create one through **Your Universe**, at the bottom left of the home screen, to keep completed results across browsers and devices.

Your Universe shows:

- Your current streak and best streak.
- Games played, total points and synonyms found.
- Your best score and average score.
- Your last three completed games and their constellations.

You can bring earlier guest games from the same browser into your account, reset your password or delete your account.

An unfinished round stays in the browser where you started it. Leaving or refreshing does not stop its clock.

## Play with friends

Share your result to compare scores on the same daily challenge. The shared text includes your constellation, points, round scores and a link to play. It leaves out your answers so friends can try it first.

Each person plays their own rounds. There is no live multiplayer lobby.

## Privacy

Usage tracking and browser error reporting are optional and off unless you agree to them. Error reporting also requires the service to be configured. The counts cover visits, game starts, completions and share-button clicks. They do not include your email, username, answers or score. Technical error reports remove raw messages and sensitive fields. Server diagnostics help keep the service working independently of browser tracking.

Use **Tracking** on the home screen to change your choice or request removal of earlier usage records from that browser.

Read the [privacy notice](https://wordstellar-application.vercel.app/privacy.html). For privacy questions or requests, contact [willowrangers23@gmail.com](mailto:willowrangers23@gmail.com).

## About the project

I built Wordstellar to make a short daily word game that also gives players something to learn between rounds. The space theme turns each accepted word into a visible part of your progress.

The interface uses HTML and CSS, TypeScript for core rules and APIs, and JavaScript for existing screens and artwork. Jost is its main typeface. Vercel hosts the app and Supabase handles accounts and saved games. Automated checks include Playwright browser journeys in GitHub Actions, with disposable test accounts separated from production.

Word meanings and candidate synonyms draw on Open English Wordnet, scoring uses wordfreq estimates, and the origin summaries were checked against the Online Etymology Dictionary. Full acknowledgements and data licences are in the app’s [word-source credits](https://wordstellar-application.vercel.app/credits.html).

This public repository contains the game overview and user guide. The application source is kept in a separate private repository.

Created by [Will Bergin](https://github.com/willbergin).

## Growing the daily word bank

The automatic replacement is implemented and awaiting one-time activation. It prepares dated sets ahead of play and permanently reserves used starting words and declared variants. It also excludes targets from the old bank. The existing daily sets continue until activation.

New sets use AI-generated original copy, retrieved dictionary evidence and automated review. AI does not judge live answers or choose their point values. Checks can still make mistakes, and familiar vocabulary is finite. A missing rolling set prompts the player to try again; it is never filled by silently recycling an old word.

## Round stars

Each round gives you one shining, animated real star, based on that round’s points:

| Round points | Star |
| --- | --- |
| 0–1 | Polaris |
| 2–3 | Deneb |
| 4–6 | Altair |
| 7–9 | Vega |
| 10+ | Sirius |

The final recap shows your five round stars, and sharing includes their names without revealing your answers. Reduced-motion settings stop the animations.

The sequence follows approximate apparent brightness from Earth. All five are Milky Way stars; distance alone does not determine brightness. The artwork is stylised. Your final constellation still depends on the total score across all five rounds, and star rewards add no extra points.
