# Spotify Playlist Language Filter

This script removes songs of a certain language from an existing playlist by creating a new one without it. It uses the Spotify API to access playlists and track information, the Genius API to fetch song lyrics, and the `langdetect` library to determine the language of the lyrics.

## Features

- Fetches songs from a specified Spotify playlist.
- Retrieves lyrics for each song using the Genius API.
- Detects the language of the lyrics.
- Filters songs based on a specified language code.
- Creates a new Spotify playlist with only the songs that match the desired language.
- Caches lyrics language detection results to minimize redundant API calls.
- Uses parallel processing to speed up lyrics fetching and analysis.

## Requirements

- Python 3.6 or higher (Might work on 3.6 or below, I never tested ¯\_(ツ)_/¯)
- Spotify Developer Account
- Genius API Token

## Installation

1. **Clone the repository:**

   ```sh
   git clone https://github.com/your-username/spotify-playlist-language-filter.git
   cd spotify-playlist-language-filter
   ```

2. **Install dependencies:**

   The script checks and installs the required packages automatically. However, you can manually install them using pip:

   ```sh
   pip install spotipy lyricsgenius langdetect
   ```

3. **Update the script with your settings:**

   Open `filter.py` and update the following variables:
   
   - `filter_language_code`: Set the desired language code (e.g., `'en'` for English, `'es'` for Spanish).
   - `original_playlist_id`: Set the Spotify playlist ID you want to filter.
   - `client_id`, `client_secret`, `genius_token`, `redirect_uri`: Set your Spotify and Genius API credentials.

## Usage

Run the script:

```sh
python filter.py
```

The script will:
1. Load the cache from `song_language_cache.json`.
2. Fetch the songs from the specified Spotify playlist.
3. Retrieve lyrics for each song using the Genius API.
4. Detect the language of the lyrics.
5. Create a new Spotify playlist containing only the songs that match the specified language.
6. Save the language detection results to the cache file.

## Configuration

- **Logging:** The script uses Python's `logging` module for logging information, warnings, and errors. By default, it logs to the console with the `INFO` level.

- **Cache:** The cache file (`song_language_cache.json`) stores the language detection results to minimize redundant API calls. Each entry is stored as a JSON object on a new line for easy readability.

## File Structure

- `filter.py`: The main script that performs the filtering.
- `song_language_cache.json`: The cache file storing language detection results.
- `README.md`: This file.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Contributing

Contributions are welcome! Please fork the repository and create a pull request with your changes.

## Acknowledgements

- [Spotipy](https://github.com/plamere/spotipy): A lightweight Python library for the Spotify Web API.
- [lyricsgenius](https://github.com/johnwmillr/LyricsGenius): A Python client for the Genius API.
- [langdetect](https://pypi.org/project/langdetect/): A port of Google's language-detection library.

## Contact

For any questions or suggestions, please open an issue on GitHub.
