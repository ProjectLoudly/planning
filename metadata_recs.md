# Metadata Recommendations
The following are recommendations for metadata that will be encoded with the audio file.  Publisher
specific data (ie: iTunes or NPR One) should be a separate issue.


## Encoding Metadata
FFMPEG's -metadata flag can encode metadata into the output files and takes care of putting it in the correct format 
for the metadata containers.
    
    `ffmpeg -i input_file.wav -metadata title="La la la title title" -metadata artist="artist McArty" temp.flac`
    
Supported metadata keys: https://wiki.multimedia.cx/index.php?title=FFmpeg_Metadata

## MP3
* ID3 is the metadata container most commonly used for MP3
* Loudly should use ID3v2 (not ID3v1), which is prepended to the start of a file to aid streaming media.

## AAC
* The MPEG-4 container that contains the AAC can support several metadata styles:
    * iTunes-style metadata (mp4v2) (https://code.google.com/archive/p/mp4v2/wikis/iTunesMetadata.wiki)
    * 3gp-style metadata
    * ID3v2 tags (http://www.mp4ra.org/specs.html#id3v2)
    
## FLAC
* Uses Vorbis comment style metadata containers (https://en.wikipedia.org/wiki/Vorbis_comment)
* FFMPEG does not support adding cover art to FLAC yet but metaflac can (https://xiph.org/flac/documentation_tools_metaflac.html):

    `--import-picture-from={FILENAME|SPECIFICATION}	`

## ID3v2 Specs
* The ID3 container consists of a header, an optional footer, and a number of frames. 
* The frames each contain a piece of metadata (https://en.wikipedia.org/wiki/ID3)

## NPR One requirements
* TBD (waiting for access to their API on Github)

## Tags for podcasts
An RSS feed is used to notify clients of podcasts and new episodes.  A sample of this feed
can be found here (https://resourcecenter.odee.osu.edu/digital-media-production/how-write-podcast-rss-xml)
* specs: https://help.apple.com/itc/podcasts_connect/#/itcb54353390
* We should implement at least the GUID tag listed in the specs above since that's how iTunes
recognizes new episodes.

## Recommended metadata tags:
* title: name of the episode or title of the piece
* author: host(s)
* album: name of the podcast series or show the piece belongs to
* track: podcast or episode number, for ordering chronologically when created or updated date is not
 available.
* copyright
* description
* year: year this piece was first published
* genre: [ podcast | speech | vocal ]
* cover art


 
