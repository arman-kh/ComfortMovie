# Schema for ComfortMovieDB

This file defines the structure of JSON files in the `movies/` folder. Each file represents one movie, identified by its IMDb ID (e.g., `tt0110357.json`), and contains metadata and a list of scenes to filter.

## File Structure
- **Root Object**: One movie per file, with these fields:
  - **`imdb_id`** (string): IMDb identifier (e.g., `"tt0110357"`). Required.
  - **`title`** (string): Movie title (e.g., `"The Lion King"`). Required.
  - **`duration`** (number): Total runtime in seconds (e.g., `5280` for 88 minutes). Required.
  - **`version`** (string): Film cut (e.g., `"theatrical"`, `"extended"`). Required.
  - **`scenes`** (array): List of scenes to flag. Optional (empty array if no scenes).

- **Scene Object**: Each scene in the `scenes` array has:
  - **`start`** (number): Start time in seconds (e.g., `45.2`). Required.
  - **`end`** (number): End time in seconds (e.g., `48.9`). Required; must be > `start`.
  - **`reason`** (string): Category of concern (e.g., `"frightening"`, `"violence"`). Required. Options:
    - `violence`, `gore`, `language`, `nudity`, `sex`, `frightening`, `drugs`, `other`
  - **`severity`** (number): Intensity, 1-5 (e.g., `3`). Optional; defaults to unset.
  - **`mute`** (boolean): Mute sound? (e.g., `true`). Optional; defaults to `false`.
  - **`skip`** (boolean): Skip scene? (e.g., `true`). Optional; defaults to `false`.
  - **`blur`** (boolean): Blur visuals? (e.g., `false`). Optional; defaults to `false`.
  - **`description`** (string): Brief note (e.g., `"Mufasa’s death"`). Optional.

## Notes
- Use seconds for `start`, `end`, and `duration` (decimals allowed, e.g., `45.2`).
- Ensure `start` < `end` and both are within `duration`.
- If no actions (`mute`, `skip`, `blur`) are set, the scene is flagged but unchanged.
- See [examples.md](examples.md) for sample files.

This schema keeps ComfortMovieDB flexible yet consistent—perfect for family filtering!
