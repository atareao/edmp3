# edmp3

A simple command line tool to edit tags of mp3 files

From [eyeD3](https://eyed3.readthedocs.io/en/latest/) documentation:

```bash
 -a STRING, --artist STRING
                        Set the artist name.
  -A STRING, --album STRING
                        Set the album name.
  -b STRING, --album-artist STRING
                        Set the album artist name. 'Various Artists', for example. Another example is collaborations when the track artist might be 'Eminem
                        featuring Proof' the album artist would be 'Eminem'.
  -t STRING, --title STRING
                        Set the track title.
  -n NUM, --track NUM   Set the track number. Use 0 to clear.
  -N NUM, --track-total NUM
                        Set total number of tracks. Use 0 to clear.
  --track-offset N      Increment/decrement the track number by [-]N. This option is applied after --track=N is set.
  --composer STRING     Set the composer's name.
  --orig-artist STRING  Set the orignal artist's name. For example, a cover song can include the orignal author of the track.
  -d NUM, --disc-num NUM
                        Set the disc number. Use 0 to clear.
  -D NUM, --disc-total NUM
                        Set total number of discs in set. Use 0 to clear.
  -G GENRE, --genre GENRE
                        Set the genre. If the argument is a standard ID3 genre name or number both will be set. Otherwise, any string can be used. Run
                        'eyeD3 --plugin=genres' for a list of standard ID3 genre names/ids.
  --non-std-genres      Disables certain ID3 genre standards, such as the mapping of numeric value to genre names. For example, genre=1 is taken literally,
                        not mapped to 'Classic Rock'.
  -Y YEAR, --release-year YEAR
                        Set the year the track was released. Use the date options for more precise values or dates other than release.
  -c STRING, --comment STRING
                        Set a comment. In ID3 tags this is the comment with an empty description. See --add-comment to add multiple comment frames.
  --artist-city STRING  The artist's city of origin. Stored as a user text frame `eyeD3#artist_origin`
  --artist-state STRING
                        The artist's state of origin. Stored as a user text frame `eyeD3#artist_origin`
  --artist-country STRING
                        The artist's country of origin. Stored as a user text frame `eyeD3#artist_origin`
  --rename PATTERN      Rename file (the extension is not affected) based on data in the tag using substitution variables: $album, $album_artist, $artist,
                        $best_date, $best_date:prefer_recording, $best_date:prefer_recording:year, $best_date:prefer_release,
                        $best_date:prefer_release:year, $best_date:year, $disc:num, $disc:total, $file, $file:ext, $original_release_date,
                        $original_release_date:year, $recording_date, $recording_date:year, $release_date, $release_date:year, $title, $track:num,
                        $track:total

ID3 options:
  -1, --v1              Only read and write ID3 v1.x tags. By default, v1.x tags are only read or written if there is not a v2 tag in the file.
  -2, --v2              Only read/write ID3 v2.x tags. This is the default unless the file only contains a v1 tag.
  --to-v1.1             Convert the file's tag to ID3 v1.1 (Or 1.0 if there is no track number)
  --to-v2.3             Convert the file's tag to ID3 v2.3
  --to-v2.4             Convert the file's tag to ID3 v2.4
  --release-date DATE   Set the date the track/album was released
  --orig-release-date DATE
                        Set the original date the track/album was released
  --recording-date DATE
                        Set the date the track/album was recorded
  --encoding-date DATE  Set the date the file was encoded
  --tagging-date DATE   Set the date the file was tagged
  --publisher STRING    Set the publisher/label name
  --play-count <+>N     Set the number of times played counter. If the argument value begins with '+' the tag's play count is incremented by N, otherwise
                        the value is set to exactly N.
  --bpm N               Set the beats per minute value.
  --unique-file-id OWNER_ID:ID
                        Add a unique file ID frame. If the ID arg is empty the frame is removed. An OWNER_ID is required. The ID may be no more than 64
                        bytes.
  --add-comment COMMENT[:DESCRIPTION[:LANG]]
                        Add or replace a comment. There may be more than one comment in a tag, as long as the DESCRIPTION and LANG values are unique. The
                        default DESCRIPTION is '' and the default language code is 'eng'.
  --remove-comment DESCRIPTION[:LANG]
                        Remove comment matching DESCRIPTION and LANG. The default language code is 'eng'.
  --remove-all-comments
                        Remove all comments from the tag.
  --add-lyrics LYRICS_FILE[:DESCRIPTION[:LANG]]
                        Add or replace a lyrics. There may be more than one set of lyrics in a tag, as long as the DESCRIPTION and LANG values are unique.
                        The default DESCRIPTION is '' and the default language code is 'eng'.
  --remove-lyrics DESCRIPTION[:LANG]
                        Remove lyrics matching DESCRIPTION and LANG. The default language code is 'eng'.
  --remove-all-lyrics   Remove all lyrics from the tag.
  --text-frame FID:TEXT
                        Set the value of a text frame. To remove the frame, specify an empty value. For example, --text-frame='TDRC:'
  --user-text-frame DESC:TEXT
                        Set the value of a user text frame (i.e., TXXX). To remove the frame, specify an empty value. e.g., --user-text-frame='SomeDesc:'
  --url-frame FID:URL   Set the value of a URL frame. To remove the frame, specify an empty value. e.g., --url-frame='WCOM:'
  --user-url-frame DESCRIPTION:URL
                        Set the value of a user URL frame (i.e., WXXX). To remove the frame, specify an empty value. e.g., --user-url-frame='SomeDesc:'
  --add-image IMG_PATH:TYPE[:DESCRIPTION]
                        Add or replace an image. There may be more than one image in a tag, as long as the DESCRIPTION values are unique. The default
                        DESCRIPTION is ''. If PATH begins with 'http[s]://' then it is interpreted as a URL instead of a file containing image data. The
                        TYPE must be one of the following: OTHER, ICON, OTHER_ICON, FRONT_COVER, BACK_COVER, LEAFLET, MEDIA, LEAD_ARTIST, ARTIST, CONDUCTOR,
                        BAND, COMPOSER, LYRICIST, RECORDING_LOCATION, DURING_RECORDING, DURING_PERFORMANCE, VIDEO, BRIGHT_COLORED_FISH, ILLUSTRATION,
                        BAND_LOGO, PUBLISHER_LOGO.
  --remove-image DESCRIPTION
                        Remove image matching DESCRIPTION.
  --remove-all-images   Remove all images from the tag
  --write-images DIR    Causes all attached images (APIC frames) to be written to the specified directory.
  --add-object OBJ_PATH:MIME-TYPE[:DESCRIPTION[:FILENAME]]
                        Add or replace an object. There may be more than one object in a tag, as long as the DESCRIPTION values are unique. The default
                        DESCRIPTION is ''.
  --remove-object DESCRIPTION
                        Remove object matching DESCRIPTION.
  --write-objects DIR   Causes all attached objects (GEOB frames) to be written to the specified directory.
  --remove-all-objects  Remove all objects from the tag
  --add-popularity EMAIL:RATING[:PLAY_COUNT]
                        Adds a pupularity metric. There may be multiples popularity values, but each must have a unique email address component. The rating
                        is a number between 0 (worst) and 255 (best). The play count is optional, and defaults to 0, since there is already a dedicated play
                        count frame.
  --remove-popularity EMAIL
                        Removes the popularity frame with the specified email key.
  --remove-v1           Remove ID3 v1.x tag.
  --remove-v2           Remove ID3 v2.x tag.
  --remove-all          Remove ID3 v1.x and v2.x tags.
  --remove-frame FID    Remove all frames with the given ID. This option may be specified multiple times.
  --max-padding NUM_BYTES
                        Shrink file if tag padding (unused space) exceeds the given number of bytes. (Useful e.g. after removal of large cover art.) Default
                        is 64 KiB, file will be rewritten with default padding (1 KiB) or max padding, whichever is smaller.
  --no-max-padding      Disable --max-padding altogether.
  --encoding latin1|utf8|utf16|utf16-be
                        Set the encoding that is used for all text frames. This option is only applied if the tag is updated as the result of an edit option
                        (e.g. --artist, --title, etc.) or --force-update is specified.

Misc options:
  --force-update        Rewrite the tag despite there being no edit options.
  -v, --verbose         Show all available tag data
  --preserve-file-times
                        When writing, do not update file modification times.
```
