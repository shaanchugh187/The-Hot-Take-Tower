# Hot Take Tower

Hot Take Tower is a party game: guess what real polls found, win blocks for close guesses, and build a tower before it collapses. Play solo, daily, or with  friends.

**Play:** _add your live link here after deploying_

## How it works
1. Each round shows a hot take, such as "Dogs are better pets than cats".
2. Slide to the percentage of people you think agree.
3. The real percentage comes from a published poll. Land within 10 points and you win a block. Miss and you lose one.
4. You start with 3 blocks. Survive 10 rounds to win. Hit zero and the tower collapses.

## Modes and extras
- **Solo**: 10 rounds. Three hits in a row make every hit after that worth 2 blocks.
- **Daily challenge**: the same 10 takes for everyone on the same date. There is no global leaderboard because there is no backend.
- **Party mode**: 2 to 5 players pass one phone. Guesses stay hidden until everyone has locked in, then all are revealed together.
- **Bet 2 blocks** (solo): land within 5 points to win 2 blocks, otherwise lose 2.
- **Ask the crowd** (solo, once per game): tells you which third of the scale the poll result is in.
- **Skip take** (solo, once per game): swaps the current take for a spare.
- **Challenge links**: add `?s=<number>` to the URL to play the exact same 10 takes. The "Challenge a friend" button builds one for you. It only works from a hosted URL, not a local file.
- **Rematch**: replay the same 10 takes.

## Run locally
Open `hot-take-tower.html` in a browser. There is no build step and no dependencies.

## Deploy
- **Link note**: the game file is `hot-take-tower.html`, not `index.html`, so a host's bare link will 404. Open `<your-link>/hot-take-tower.html`, or add an `index.html` containing `<meta http-equiv="refresh" content="0; url=hot-take-tower.html">` to redirect.
- **GitHub Pages**: Settings, then Pages, then deploy from the `main` branch root.
- **Vercel**: run `npx vercel --prod` in the project folder, or import the GitHub repo.
- **Netlify**: drag the folder onto Netlify Drop.

## Poll data and sources
All poll numbers live in the `TAKES` array at the top of the script. Each take has a source label with its year and a link. I checked each linked page against its number when this README was written.

| Take | % | Source |
|---|---|---|
| Pineapple on pizza is good | 59 | YouGov spring 2023, US (via Wonderopolis) |
| Rather get a text than a call | 55 | YouGov 2020, UK |
| Breakfast is the most important meal | 63 | YouGov 2023, 18 countries |
| Book is better than the movie | 72 | YouGov 2012, UK |
| Dogs are better pets than cats | 73 | Gallup 2001, US |
| Social media is bad for the country | 64 | Pew July 2020, US |
| Receiving voice notes is annoying | 30 | Preply 2023, US (via Voxbooster) |
| I like sending voice notes | 16 | YouGov 2022, UK |
| I'd quit if forced back to the office | 46 | Pew Oct 2024, US remote-capable workers |
| Hybrid beats full-time remote | 72 | Pew Oct 2024, US hybrid workers |
| Texting is my favorite way to communicate | 21 | SurveyMonkey for Axios, Nov 2018, US |
| Fight Club movie beats the book | 58 | YouGov 2016, UK, people who know both |

To add a take, add one line to `TAKES` with `cat`, `t`, `pct`, `src` and `url`. Do not invent or round a number; use the figure the source reports.

## Known limits
- The pool has 12 takes and a game uses 10, so games repeat quickly.
- The polls come from different countries and years, so no take measures one single population. Some are old: the dogs-versus-cats result is from 2001.
- Two sources are secondary reports: Wonderopolis (summarising YouGov) and Voxbooster (summarising Preply). Replace them with the original publication if you find it.
- Daily results are not synchronised between players. Players compare scores by sharing them.

## Files
- `hot-take-tower.html`: the whole game (HTML, CSS and JavaScript).
- `README.md`: this file.
