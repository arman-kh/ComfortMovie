# Examples for ComfortMovieDB

Here are sample JSON files and usage ideas to show how ComfortMovieDB works. These live in the `movies/` folder, named by IMDb ID (e.g., `tt0110357.json`).

## Example 1: The Lion King
File: `movies/tt0110357.json`
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
      "description": "Mufasa’s death scene—intense for kids"
    },
    {
      "start": 72.0,
      "end": 73.5,
      "reason": "violence",
      "severity": 2,
      "blur": true,
      "description": "Scar threatens Simba"
    }
  ]
}
