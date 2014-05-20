synology-transcode
==================

Transcode high quality audio files automatically to mp3, package for Synology
DiskStation and related products.

It's a script. You need to ssh into the box and run it by hand. But it installs
nicely.


Usage
=====

Create a `.synology-transcode` file in INI format in the directory you want to
run the script in, or in your user's home directory. Then run
`synology-transcode`.


Configuration Example
=====================

```ini
[directories]
sources = /some/path
  /some/other/path
target = /target/path

[filters]
includes = *.flac *.wav
excludes = @eaDir
```

- Separate source paths with newline.
- There is only one target path.
- Separate includes and excludes with spaces (yeah, boo, I know).
- Includes and excludes are optional. Above are the defaults.
- It makes sense to exclude `@eaDir`, so do that.


Nice-To-Haves
=============

- A user interface
- A background service

I'm too lazy to build them at this stage.


Releases
========

Find them in the `result_spk` directory.


License
=======

The license is in the `LICENSE` file. It's probably bad form to name this package
`synology-*`, but I wasn't feeling creative. Similarly, the icon is derived from
the [ffmpeg](http://www.ffmpeg.org/) project, because, guess what, `ffmpeg` is
what this script uses under the hood.

So if you have legal claim to either, drop me a line. I've no interest in
infringing, this is just a lazy side project for me.


Build
=====

1. `wget http://sourceforge.net/projects/dsgpl/files/toolkit/pkgscripts.tgz`
1. `pkgscripts/EnvDeploy -v 5.0`
1. `sudo sudo pkgscripts/PkgCreate.py -x0 -c synology-transcode`
