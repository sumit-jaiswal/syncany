Change Log
==========

### Release 0.1.3-alpha (Date: tbd.)

- Developer/alpha release (**STILL NOT FOR PRODUCTION USE!**)
- Features:
  + [WebDAV](https://github.com/syncany/syncany-plugin-webdav) now supports HTTP
    and HTTPS (ask user for certificate confirmation) #50
  + [SFTP](https://github.com/syncany/syncany-plugin-sftp) now implements strict
    host checking (ask user for host fingerprint confirmation) #127
- Windows-specific:
  + Set JAVA_HOME during installation #121/#122
  + Replace uninstall icons with high-depth icons
  + Ship 'sy.bat' to allow `sy` command on Windows (not only `syncany`)
- Bugfixes:
  + Fix S3 plugin connect failure (delete repo file) #128
  + Proper remote locking for cleanup through action files #104
  
### Release 0.1.2-alpha (Date: 27 Apr 2014)

- Developer/alpha release (**NOT FOR PRODUCTION USE!**)
- Features:
  + Extracted non-core plugins, allow easy plugin installation through
    `sy plugin (list|install|remove)` #26/#104
    - Shipped plugins now only 'local'
    - Installable plugins:
      [FTP](https://github.com/syncany/syncany-plugin-ftp),
      [SFTP](https://github.com/syncany/syncany-plugin-sftp) (no host checking),
      [WebDAV](https://github.com/syncany/syncany-plugin-webdav) (HTTP only),
      [Amazon S3](https://github.com/syncany/syncany-plugin-s3)
  + Ignore files using wildcards in .syignore (e.g. *.bak, *.r??) #108
  + Added Arch Linux 'syncany-git' package #99
  + Allow speicifying HTTP(S)/WebDAV proxy and other global system properties #109
- Bugfixes:
  + Fix semantic in TransferManager `test()` (incl. all plugins) #103/#102
  + WebDAV plugin fix to create "multichunks"/"databases" folder #110
  + Fix "Plugin not supported" stack trace #111
  + Windows build script fix for "Could not normalize path" #107
  + Fix database file name leak of username and hostname #114
  + Check plugin compatibility before installing (check appMinVersion) #104
  + Don't ignore local/remote notifications if sync already running #88
  + Uninstall plugins on Windows (JAR locked) #113/#117
  + Rotate logs to max. 4x25 MB #116
  + Fix multichunk resource close issue #118/#120
  
### Release 0.1.1-alpha (Date: 14 Apr 2014)

- Developer/alpha release (**NOT FOR PRODUCTION USE!**)
- Features:
  + Ignoring files using .syignore file #66/#77
  + Arch Linux package support; release version #80 and git version #99
  + Additional command-specific --help texts
- Windows-specific: 
  + Add Syncany binaries to PATH environment variable during setup #84/#91
  + Fixed HSQLDB-path issue #98
- Bugfixes:
  + Timezone fix in tests #78/#90
  + Reference issue "Cannot determine file content for checksum" #92/#94
  + Atomic 'init' command (rollback on failure) #95/#96
- Other things:
  + Tests for 'connect' command  
  + Tests for .syignore

### Release 0.1.0-alpha (Date: 30 March 2014)

- First developer/alpha release (**NOT FOR PRODUCTION USE!**)
- Command line interface (CLI) with commands
  + init: initialize local folder and remote repository
  + connect: connect to an existing remote repository
  + up: index and upload local files
  + down: download changes and apply locally
  + status: list local changes
  + ls-remote: list remote changes
  + watch: watches local dir, subscribes to pub/sub, and calls down/up 
           command in a set interval
  + restore: restores a given set of files (experimental)
  + log: Outputs formatted file histories (experimental)
  + genlink: Generates syncany:// links to share
  + cleanup: Deletes old file versions and frees remote space
- Storage plugins:
  + Local: Allows to store repository files in a local/mounted folder 
  + FTP: Allows the use of an FTP folder as repository
  + WebDAV: Allows using a WebDAV folder as repository (currently no HTTPS)
