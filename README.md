# google-play-music-star-ratings
Replaces thumbs up/down buttons with 5-star ratings in google play music browser app. Available are jQuery and vanilla JavaScript versions.

To be used with **Greasemonkey** in Firefox or **Tampermonkey** in Chrome.

If you encounter *Uncaught TypeError: Illegal invocation* in Chrome, you may need to update Tampermonkey to the latest beta version.

#Notes on behavior

Part of the script concerned with updating ratings on the bottom toolbar (*'#player'*) works by first trying to grab *'data-rating'* of *'tr.currently-playing'* from main song playlist (*'#music-content .song-table'*). If the element isn't available (as it isn't always on screen), then it tries to grab *'data-rating'* from the miniqueue (*'#queue-overlay .song-table.mini'*) that is always on screen.

The problem with the miniqueue is that when it contains more than 10 songs, it is dynamically populated on opening. Thus, there may not be *'tr.currently-playing'* in the DOM for songs after the 10th in the queue. In that case the script will attempt to open the minique and refetch the rating.

Therefore expect the minique to reopen on each song past 10th, or just leave it open.

#License

Licensed under the MIT license.
