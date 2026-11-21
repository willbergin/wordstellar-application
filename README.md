# Wordstellar

**Illuminate your lexicon.**

[Play Wordstellar](https://wordstellar-application.vercel.app/) · [User guide](USER_GUIDE.md)

## What it is

Wordstellar is a daily synonym game with a space theme. You get five words, one at a time, and 30 seconds to find as many synonyms as you can. Every accepted answer lights a star. Less familiar answers earn more points, and your total reveals a constellation.

You do not need to be an etymology expert. Each word comes with a definition and an example sentence, followed by a short explanation of its origins after the round.

I built Wordstellar to make a short daily game that gives people something to learn as well as a score to compare with friends.

This public repository contains the project overview and player guide. The application source is kept in a separate private repository.

## Key features

- **A shared daily challenge:** five familiar words, five 30-second rounds and a reset at midnight UTC. There is no harder final round.
- **Weighted scoring:** common synonyms earn 1 point, uncommon synonyms 2 and rare synonyms 3. Repeats do not score again, and rejected attempts do not lose points.
- **Something to learn:** word-origin explanations and other possible answers between rounds.
- **Round stars:** Polaris, Deneb, Altair, Vega or Sirius, based on each round's score.
- **A final constellation:** Delphinus, Lyra, Aquila, Cygnus or Orion, based on total points. Orion starts at 20.
- **Sharing without spoilers:** a result includes your constellation, points, round stars and a dated challenge link, leaving out your answers.
- **Guest play:** start without registration and keep progress in the same browser.
- **Your Universe:** optional accounts with completed results across devices, current and best streaks, all-time statistics and the last three games.
- **Account controls:** import your own guest games, recover a password or delete an account.
- **An interactive observatory:** telescope launch, moving stars, planets and rockets, with reduced-motion support.
- **Optional tracking:** usage counts and browser error reports require consent. You can decline and keep playing.

The current game draws from **50 starting words across a 180-day repeating schedule**. Words repeat; this is not a promise of new words forever. Automatic AI word preparation has been built but is paused to avoid paid API usage. Playing and checking answers make no AI requests.

There is no practice mode or live multiplayer lobby. Friends compare their own attempts at the same daily challenge. The [user guide](USER_GUIDE.md) explains the rules and reward bands.

## Tech stack

| Area | Technology |
| --- | --- |
| Interface | HTML, CSS and SVG, with locally served Jost typography and custom space illustrations. |
| Application code | TypeScript for core rules, daily state, APIs, diagnostics and shared views; JavaScript for existing controllers and artwork. |
| Build | Node.js and esbuild. |
| Hosting | Vercel static hosting and serverless API functions. |
| Accounts and saved results | Supabase Auth and PostgreSQL, with browser storage for guest and unfinished progress. |
| Testing | Node.js tests, jsdom, PGlite and Playwright browser journeys. |
| Continuous integration | GitHub Actions, including account tests with disposable local services. |
| Error reporting | Sentry, with sanitised reports and consent for browser diagnostics. |
| Word data | Open English Wordnet, wordfreq familiarity estimates and researched word origins. |

There is no React, Next.js or third-party UI component library. The optional OpenAI integration is not active in the current word-bank setup.

## Technical decisions and trade-offs

| Decision | Reason | Trade-off |
| --- | --- | --- |
| Keep the frontend lightweight | Plain browser code suits a small project maintained by one creator. | Custom screen controllers and styles need ongoing maintenance as the game grows. |
| Introduce TypeScript gradually | Shared rules and APIs can be checked without rewriting the whole interface. | Some screens and illustrations still use JavaScript. |
| Check a fixed list of synonyms | Answers and scores stay consistent, with no model delay or AI charge during play. | A valid synonym may be missing from the list or may fit a different meaning. |
| Keep the existing word bank | The current game does not need paid AI preparation. | Starting words repeat, and expanding the bank requires a content update. |
| Use word frequency for scoring | It gives a consistent guide to how familiar an answer is. | A long word is not automatically rare, and frequency does not measure complexity exactly. |
| Let guests start immediately | People can try the game without sharing an email. | Guest and unfinished progress belongs to that browser and can disappear if site data is cleared. |
| Make accounts optional | Completed results can follow players across devices. | Accounts rely on external authentication, database and email services. Unfinished rounds remain local. |
| Recalculate saved scores | The server checks accepted answers instead of trusting a submitted total. | Browser timers and downloadable answer lists mean this remains a casual game, not a verified competitive system. |
| Keep the space artwork custom | Stars and constellations make progress visible and give the game its identity. | Bespoke styles and animations need responsive and reduced-motion checks. |
| Ask before tracking usage | Refusing optional tracking does not change the game. | Usage reports cover consenting browsers rather than every player. |

The design-system cleanup keeps the observatory and reward artwork, while giving buttons, forms, dialogs and feedback a consistent set of styles and interaction states. Jost is served with the site. Desktop and mobile checks include reference screenshots; real-device checks remain separate.

## Privacy and sources

Use **Tracking** on the home screen to change your preference or request removal of earlier usage records from that browser. Account deletion is available in **Your Universe**. Server diagnostics operate separately from optional browser tracking, with sensitive fields removed.

Read the [privacy notice](https://wordstellar-application.vercel.app/privacy.html) or contact [willowrangers23@gmail.com](mailto:willowrangers23@gmail.com) with a privacy question.

Word-source acknowledgements and data licences are available in the app's [credits](https://wordstellar-application.vercel.app/credits.html). The constellation bands are game rewards, not an astronomical brightness ranking. Round stars follow approximate apparent brightness from Earth; the artwork is stylised.

Created by [Will Bergin](https://github.com/willbergin).
