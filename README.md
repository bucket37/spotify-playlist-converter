# Spotify Playlist Downloader

A powerful GUI application that allows you to download songs from Spotify playlists as MP3 files. It supports playlists of any size (including those over 1000 songs) and provides both regular and debug versions.

## Quick Start (Pre-compiled Version)

1. Download `SpotifyDownloaderSetup.exe`
2. Run the installer
3. Choose installation options (desktop shortcut, etc.)
4. Launch the application from Start Menu or Desktop
5. Enter your Spotify playlist URL and start downloading!

## Manual Installation

1. Download `SpotifyDownloader_Manual.zip`
2. Extract to your preferred location
3. Run `SpotifyDownloader.exe` for the regular version
   - Or `SpotifyDownloader_Debug.exe` for troubleshooting

## Development Setup (Source Code)

### Prerequisites

- Python 3.7 or higher
- FFmpeg installed on your system
- Spotify Developer Account

### Installation from Source

1. Download and extract `SpotifyDownloader_Source.zip`

2. Install required packages:
```bash
pip install -r requirements.txt
```

3. Install FFmpeg:
   - Windows: Download from https://ffmpeg.org/download.html and add to PATH
   - Mac: `brew install ffmpeg`
   - Linux: `sudo apt-get install ffmpeg`

4. Set up Spotify API credentials:
   - Go to https://developer.spotify.com/dashboard
   - Create a new application
   - Get your Client ID and Client Secret
   - Create a `config/credentials.json` file with:
   ```json
   {
       "client_id": "your_client_id_here",
       "client_secret": "your_client_secret_here"
   }
   ```

### Running from Source

Regular version (GUI):
```bash
python spotify_downloader_gui.py
```

Command-line version:
```bash
python spotify_downloader.py <playlist_url>
```

### Building the Executable

1. Install PyInstaller:
```bash
pip install pyinstaller
```

2. Build using the spec file:
```bash
pyinstaller spotify_downloader.spec
```

This will create both regular and debug versions in the `dist` directory.

## Features

- Download playlists of any size (1000+ songs supported)
- GUI interface with progress tracking
- Automatic rate limiting to prevent API issues
- High-quality MP3 downloads
- Debug version for troubleshooting
- Persistent download progress tracking
- Configurable download directory

## Project Structure

```
spotify_downloader/
├── spotify_downloader_gui.py  # Main GUI application
├── spotify_downloader.py      # Core functionality
├── requirements.txt          # Python dependencies
├── config/                   # Credentials and settings
└── downloads/               # Default download location
```

## Troubleshooting

1. If downloads fail:
   - Check your internet connection
   - Try using the debug version
   - Verify your Spotify credentials
   - Check the download directory permissions

2. If the GUI doesn't start:
   - Run the debug version to see error messages
   - Verify Python and dependencies are installed
   - Check your antivirus isn't blocking the application

## Known Issues

- Some special characters in song titles may be replaced
- Rate limiting might slow down large playlist downloads
- FFmpeg must be installed separately for the source version

## Legal Notice

This tool is for personal use only. Please respect copyright laws and terms of service for both Spotify and YouTube.

## Updates

### Latest Changes
- Added installer for easy deployment
- Improved large playlist support (1000+ songs)
- Switched to JSON-based credential storage
- Added debug version for troubleshooting
- Fixed tqdm progress bar issues
- 
