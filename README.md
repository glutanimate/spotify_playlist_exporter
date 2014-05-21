## README for spotify_playlist_exporter

###Description

![image of main interface](https://raw.githubusercontent.com/Glutanimate/spotify_playlist_exporter/master/spotify_playlist_exporter_main.png)

![image of progress window](https://raw.githubusercontent.com/Glutanimate/spotify_playlist_exporter/master/spotify_playlist_exporter_progress.png)

This script exports Spotify playlists to a plain textfile. It works by iterating through Spotify URIs and querying Spotify's web API for the track data.

###Overview

    # NAME:         spotify_playlist_exporter
    # VERSION:      0.2
    # AUTHOR:       (c) 2014 Glutanimate <https://github.com/Glutanimate/>
    # DESCRIPTION:  Exports spotify playlists to a plain textfile
    # CHANGELOG:    -- 0.2 - Script now uses Spotify's web API
    #               -- 0.1 - Initial release
    # DEPENDENCIES: curl yad jq
    # SOURCES:      https://developer.spotify.com/technologies/web-api/lookup/
    #
    # LICENSE:      GNU GPLv3 (http://www.gnu.de/documents/gpl-3.0.en.html)
    #
    # NOTICE:       THERE IS NO WARRANTY FOR THE PROGRAM, TO THE EXTENT PERMITTED BY APPLICABLE LAW. 
    #               EXCEPT WHEN OTHERWISE STATED IN WRITING THE COPYRIGHT HOLDERS AND/OR OTHER PARTIES 
    #               PROVIDE THE PROGRAM “AS IS” WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESSED OR 
    #               IMPLIED, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY 
    #               AND FITNESS FOR A PARTICULAR PURPOSE. THE ENTIRE RISK AS TO THE QUALITY AND 
    #               PERFORMANCE OF THE PROGRAM IS WITH YOU. SHOULD THE PROGRAM PROVE DEFECTIVE,
    #               YOU ASSUME THE COST OF ALL NECESSARY SERVICING, REPAIR OR CORRECTION.
    #
    #               IN NO EVENT UNLESS REQUIRED BY APPLICABLE LAW OR AGREED TO IN WRITING WILL ANY 
    #               COPYRIGHT HOLDER, OR ANY OTHER PARTY WHO MODIFIES AND/OR CONVEYS THE PROGRAM AS 
    #               PERMITTED ABOVE, BE LIABLE TO YOU FOR DAMAGES, INCLUDING ANY GENERAL, SPECIAL, 
    #               INCIDENTAL OR CONSEQUENTIAL DAMAGES ARISING OUT OF THE USE OR INABILITY TO USE 
    #               THE PROGRAM (INCLUDING BUT NOT LIMITED TO LOSS OF DATA OR DATA BEING RENDERED 
    #               INACCURATE OR LOSSES SUSTAINED BY YOU OR THIRD PARTIES OR A FAILURE OF THE 
    #               PROGRAM TO OPERATE WITH ANY OTHER PROGRAMS), EVEN IF SUCH HOLDER OR OTHER 
    #               PARTY HAS BEEN ADVISED OF THE POSSIBILITY OF SUCH DAMAGES.
    #
    # USAGE:        Select all items in your Spotify playlist, right click and select 'Copy Spotify URIs',
    #               paste the output in them ultiline entry field. Make sure to also enter a name for the 
    #               playlist. Then hit 'OK'.

###Changelog

- 0.2
    - the script now uses Spotify's web API. Everything should be much faster.
- 0.1 
    - initial release

###Dependencies

`curl` and `jq` should be available in your standard repositories. You can install them with

    sudo apt-get install curl jq
   
[YAD](http://sourceforge.net/projects/yad-dialog/) is an advanced fork of Zenity. Unfortunately it hasn't arrived in the Debian/Ubuntu repos yet but luckily enough the folks over at www.webupd8.com created a PPA for it. You can add the YAD PPA and install YAD with:

    sudo add-apt-repository ppa:webupd8team/y-ppa-manager
    sudo apt-get update
    sudo apt-get install yad

###Installation

1. Grab the latest source tarball and extract it.

2. Copy `spotify_playlist_exporter` to your `$PATH` (e.g. `~/bin` for single user installation or `/usr/local/bin` for multi user installation)

3. Copy `spotify_playlist_exporter.desktop` to `~/.local/share/applications` for single user installation or `/usr/local/share/applications` for multi user installation)

Spotify Playlist Epxorter should now appear in your launcher (e.g. Unity dash).

###Usage

Select all items in your Spotify playlist, copy them, and paste the output in the multiline entry field. Make sure to enter a name for the playlist. Then hit 'OK'.

###Common issues

**The playlist export is taking very long to complete**

`spotify_playlist_exporter` fetches the track data for each item separately. This might take a while with larger playlists.
