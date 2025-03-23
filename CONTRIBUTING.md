# Contributing to MovieHavenDB

Thanks for helping make **MovieHavenDB** a better resource for comfy movie nights! This is a slow-growing, volunteer-driven project, so every scene you add counts—whether it’s one movie a month or a quick fix. Here’s how to contribute.

## How to Add a Movie
1. **Pick a Movie**: Choose a film you’ve watched. Find its IMDb ID (e.g., `tt0110357` for *The Lion King*) on [imdb.com](https://www.imdb.com).
2. **Watch & Log**: Note any scenes you’d flag as “inappropriate” (e.g., violence, language). Use a player like VLC (press `Ctrl+J` for seconds) to get exact start and end times.
3. **Format It**: Create a JSON file matching our schema—see [docs/schema.md](docs/schema.md) for details. Name it with the IMDb ID (e.g., `tt0110357.json`).
4. **Submit It**: Add your file to the `movies/` folder via a pull request (PR). No Git skills? Use GitHub’s web interface—see below!

### Example
For *The Lion King*:
```json
{
  "imdb_id": "tt0110357",
  "title": "The Lion King",
  "duration": 5280,
  "version": "theatrical",
  "scenes": [
    {
      "start": 45.2,
      "end": 48.9,
      "reason": "frightening",
      "severity": 3,
      "mute": true,
      "skip": true,
      "description": "Mufasa’s death scene"
    }
  ]
}
```
Guidelines
Timestamps: Use seconds (e.g., 45.2) from the movie’s start. Double-check they fit the duration.

Reasons: Pick from: violence, language, nudity, sex, frightening, drugs, gore, other. Add a short description if it helps.

Actions: Set mute, skip, or blur to true/false (default is false if omitted).

Version: Specify the cut (e.g., theatrical, extended)—scenes shift between edits!

Quality: Verify your times; overlaps are okay but keep them sensible.

Submitting via GitHub Web
Go to ComfortMovieDB repo.

Click “Create new file” in movies/.

Name it (e.g., movies/tt0110357.json), paste your JSON, and write a commit message (e.g., “Added The Lion King scenes”).

Select “Create a new branch and start a pull request”, then click “Propose new file”.

Add a PR title (e.g., “Add tt0110357 scenes”) and hit “Create pull request”.

Submitting via Git (Optional)
Clone the repo: git clone https://github.com/arman-kh/MovieHavenDB.git.

Create a branch: git checkout -b add-movie-tt0110357.

Add your file to movies/, commit it: git add . && git commit -m "Add The Lion King scenes".

Push it: git push origin add-movie-tt0110357.

Open a PR on GitHub.


