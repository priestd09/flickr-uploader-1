# flickr-uploader
## What?

This script helps you to upload a lot of pictures to Flickr. If the upload fails, you can resume at the last uploaded picture. Also if you uploaded something wrong, you can delete whole photosets including all photos in it.

## Installation

It's a ruby script. I used ruby 2.0 for development, but it should also run with ruby 1.9.x. Packet management is done via bundler.

```
  gem install bundler
  bundle install
```

## Usage
### Examples

`ruby flickr-uploader.rb --help`
`ruby flickr-uploader.rb --upload "/Users/johan/Pictures/vacation"

### Authentication

To access your Flickr account, you need to be authenticated. This happens either when you first use the tool, or you can prompt the authentication flow via `ruby flickr-uploader.rb --connect`. You will need to open a URL in your browser and then copy/paste the shown number back into the terminal.

If you want to connect a new account, just start the connect flow again with the above-mentioned command.

### Uploading all files in a directory

flickr-uploader assumes that you want to upload all files (photos and videos) within one directory. Please make sure that no other files are present in the directory.

Start the upload via `ruby flickr-uploader.rb --upload DIRECTORY`. Use the absolute path to the directory. If you specify a photoset name via `--photoset-name NAME` all uploaded items will be added to that newly-created photoset. By default, all photos are uploaded privately. You can upload items publicly via the `-p` switch.

### Deleting all items in a photoset

To delete all items in a photoset, use `ruby flickr-uploader.rb --delete-photoset PHOTOSET_ID`. To get the photoset_id, either go to the photoset on Flickr and copy the id from the URL, or list all your photosets via `ruby flickr-uploader.rb --list-photosets`.

### Dry mode

If you run any command with the `-d` switch, it will still show the output but no actions will actually happen.

## Contributing
Fork away. I'm happy to accept pull requests, there is a lot of stuff to be added.