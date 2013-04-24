iTunes Sync Bitcasa
================================================================================

Backup from local iTunes music library to Bitcasa.


Requirements
--------------------------------------------------------------------------------

- OSX Mountain Lion 10.8.3
- Bitcasa 1.04


Installation
--------------------------------------------------------------------------------

Clone this repository your local machine.

```sh
$ git clone git://github.com/Tomohiro/itunes-sync-bitcasa.git
```

Copy the `itunes-sync-bitcasa` command to your `~/bin` directory like below.

```sh
$ cd itunes-sync-bitcasa
$ cp ./itunes-sync-bitcasa ~/bin/
```


Backup flow
--------------------------------------------------------------------------------

### Default directory paths

Source                           | Destination
-------------------------------- | ---------------------------------------------
`$HOME/Music/iTunes Media/Music` | `/Volumes/Bitcasa Infinite Drive/Music/iTunes/iTunes Media/Music`

### Backup

```sh
$ itunes-sync-bitcasa
```

If you want change the source or destination paths, you can type following command.

```sh
$ ITUNES_SOURCE="~/Music" BITCASA_TARGET="/Volumes/Bitcasa Infinite Drive/MusicBackup/Music" itunes-sync-bitcasa
```

After backup, you can execute rsync in safety like below.

```sh
$ rsync -avP --delete '~/Music/iTunes Media/iTunes Media/Music/' '/Volumes/Bitcasa Infinite Drive/Music/iTunes Media/Music/'
```


LICENSE
--------------------------------------------------------------------------------

&copy; 2013 Tomohiro TAIRA.
This project is licensed under the MIT license.
See LICENSE for details.
