# Vocab Trainer

A remake of the old Quizlet "Write" mode: you see the German word and type the translation. Small typos are caught and you retype them. Words come in rounds of 7 new + 3 review, and a round counts as done at 80%.

## Run it

It's a single HTML file with no build step. It just needs to be served over http, because browsers block the word lists when you open the file directly:

```
git clone <this repo>
cd vokabeln
python3 -m http.server 8000
```

Then open http://localhost:8000. Your progress is saved in that browser (localStorage).

To get new lists: `git pull`, then reload. New lists are added automatically.

## Lists

`listen/*.txt` holds one pair per line: `prompt = translation` (the prompt is German by default; a bundled list can set `from: "zh"` etc.). The separator can be tab, `=`, `;` or ` - `. Use `/` for several correct answers. Put the words in order from easy to hard, since new words are introduced in file order.
To bundle a list, add it to the `BUNDLED` array in `index.html`. You can also import your own lists in the app.
