# Spotify WhoDis Alfred Workflow

A simple [Alfred workflow](https://www.alfredapp.com/workflows/) to show the currently playing Spotify song, artist and track in a macOS notification via a hotkey

## Prerequisites

- [Alfred](https://www.alfredapp.com/) - Free
- [Alfred PowerPack](https://www.alfredapp.com/powerpack/) - 💰

## Download and Install

1. Download latest version (1.0.0) here: [WhoDis.alfredworkflow](https://github.com/blackspike/spotify-whodis-alfred-workflow/releases/latest)
2. Double click the `WhoDis.alfredworkflow` file and it will install

## Preview

![Who Dis notification preview](./preview.png?raw=true)

## Applescript

```applescript
on alfred_script(q)

	tell application "Spotify"
		set ctrack to the current track
		set cartist to the artist of ctrack as text
		set cname to the name of ctrack as text
		set calbum to the album of ctrack as text

		set strJSON to "{\"alfredworkflow\": {\"variables\": {"

		set strJSON to strJSON & "\"NAME\": \"" & cname & "\", "
		set strJSON to strJSON & "\"ARTIST\": \"" & cartist & "\", "
		set strJSON to strJSON & "\"ALBUM\": \"" & calbum & "\", "

		set strJSON to strJSON & "}}}"

		return strJSON

	end tell

end alfred_script
```

![Who Dis icon](./SpotifyWhoDis-small.png?raw=true)
