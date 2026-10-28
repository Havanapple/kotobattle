# Kotobattle

A two-team classroom word game played on a blocky map of Japan's 47 prefectures. Teams claim and steal prefectures by playing words. It is a single HTML file with no dependencies.

## How to play

- Red starts in Okinawa and Blue starts in Hokkaido. These home bases can't be taken.
- On your turn, click a prefecture and type a word. The app counts the letters and shows the letter and score on the map (for example `A7`).
- You can only take a prefecture that touches one you own, or is across a dashed crossing from one (for example Aomori to Hokkaido, Yamaguchi to Fukuoka, Hiroshima or Oita to Ehime, Hyogo or Wakayama to Tokushima, Kagoshima to Okinawa).
- A new area needs a word that starts with the current letter.
- To steal a prefecture, use a word that starts with that area's own letter and scores more points than the current word. Ties don't steal.
- Each word can only be used once per game.
- Words are not checked against a dictionary. The game master judges whether a word is real.

## Game modes (Settings, gear icon)

- **Random letter** (default): opening an unclaimed prefecture rolls a letter in the dialog. The roll lasts the whole turn. Each player gets a limited number of re-rolls per game (shown with a dice icon on the player tags). A countdown timer (default 60 seconds) is a visual cue only. Letters can be removed from the pool, and letters that have been used come up less often.
- **Shiritori:** the next word must start with the last letter of the previous word. Blacklisted letters are skipped (FOX becomes O if X is blacklisted). Free choice lets the next player start with any letter.

## Turns

- Turns alternate between Red and Blue. The round number is shown beside the title, and the active team's tag is highlighted.
- **Pass** (skip icon) ends your turn without taking anything or scoring. **Undo** steps back one move. **Swap turn** fixes an out-of-order turn.
- Game end options: unlimited, a number of rounds, or full board (the round is finished first so both teams get the same number of turns). The winner is decided by most areas or most points.

## Other settings

- Label language: English, 日本語 or both.
- Light, dark or automatic theme.
- Animations (colour sweep and steal banner) on or off. They switch off automatically on devices set to reduce motion.
- Bonus words: a list of words that score extra, either `+x` or `×x` (halves allowed, rounded up). The bonus counts as the word's score.
- Who goes first, re-rolls per player, game end, and how the winner is decided.
- Reset board and End game now.

## Run it

Open `index.html` in a browser. Nothing else is needed.

## Put it online with GitHub Pages

1. Sign in to GitHub and create a new repository, for example `kotobattle`. Make it **Public** (Pages on private repositories needs a paid plan).
2. On the repository page choose **Add file → Upload files**, drag in `index.html` (and `README.md` if you like), then click **Commit changes**.
3. Go to **Settings → Pages**.
4. Under **Build and deployment**, set **Source** to **Deploy from a branch**. Choose branch **main** and folder **/ (root)**, then click **Save**.
5. Wait a minute or two and refresh the Pages settings. The address appears there, in the form `https://YOUR-USERNAME.github.io/kotobattle/`.

To update the game later, upload a new `index.html` with the same name (Add file → Upload files, then commit). After the update goes live, do a hard refresh in the browser (Ctrl+Shift+R, or Cmd+Shift+R on a Mac) to be sure you're seeing the new version.

## Saving

The game saves automatically in the browser's local storage, so it stays on one device and browser and is tied to the web address. A game started on one address (for example your GitHub Pages link) won't appear on another. Clearing site data clears the game.

## Rebuilding from source

The game is generated from `build.py` and `P.js` (the map). See `NOTES.md`. In short:

    python3 build.py

writes a fresh `index.html` next to the script.
