# AI Usage


# Codebase Map
## Main Files

- **`app.py`** — Creates and configures the Flask application, initializes SQLAlchemy, and registers the route blueprints for songs, playlists, users, and the feed.
- **`models.py`** — Defines the database models and relationships, including `User`, `Song`, `Playlist`, `ListeningEvent`, `Rating`, and `Notification`. It also contains association tables for relationships such as friendships and playlist songs.
- **`seed_data.py`** — Populates the database with sample users, songs, playlists, and other data for development/testing.

### `routes/`

- **`routes/songs.py`** — Handles song-related API endpoints such as searching, rating songs, and recording listening events.
- **`routes/playlists.py`** — Handles creating playlists, retrieving playlists, and adding songs to playlists.
- **`routes/users.py`** — Handles user information, listening streaks, and notifications.
- **`routes/feed.py`** — Handles endpoints for viewing friends' listening activity.

### `services/`

- **`streak_service.py`** — Contains the logic for updating and tracking listening streaks.
- **`feed_service.py`** — Builds the friends' listening/activity feeds.
- **`search_service.py`** — Handles searching for songs and retrieving song information.
- **`notification_service.py`** — Creates, retrieves, and manages notifications triggered by user actions.
- **`playlist_service.py`** — Contains playlist-related business logic.

## Data Flow: Adding a Song to a Playlist

When a user adds a song to a playlist:

```text
POST /playlists/<playlist_id>/songs
        ↓
routes/playlists.py
        ↓
notification_service.add_to_playlist()
        ↓
Add song to playlist
        ↓
Check original song sharer
        ↓
create_notification()
        ↓
Notification saved to database
```

# Root Cause Analysis
## Issue 1:

## Issue 2:
 
## Issue 3: