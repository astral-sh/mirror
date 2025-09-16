Mirrors of dependencies
===

This repository keeps mirrors of tarballs and other artifacts used by Astral CI builds (mostly for
[python-build-standalone](https://github.com/astral-sh/python-build-standalone)), to reduce both
our load on upstream hosts and build flakiness from those hosts.

The repository is deployed via GitHub Pages, so you can access the files at corresponding URL paths
in `https://astral-sh.github.io/mirror/files/`:

* [autoconf-2.72.tar.gz](https://astral-sh.github.io/mirror/files/autoconf-2.72.tar.gz)
  * mirrored from `https://ftp.gnu.org/gnu/autoconf/autoconf-2.72.tar.gz`
* [binutils-2.43.tar.xz](https://astral-sh.github.io/mirror/files/binutils-2.43.tar.xz)
  * mirrored from `https://ftp.gnu.org/gnu/binutils/binutils-2.43.tar.xz`
* [bzip2-1.0.8.tar.gz](https://astral-sh.github.io/mirror/files/bzip2-1.0.8.tar.gz)
  * mirrored from `https://sourceware.org/pub/bzip2/bzip2-1.0.8.tar.gz`
* [m4-1.4.19.tar.xz](https://astral-sh.github.io/mirror/files/m4-1.4.19.tar.xz)
  * mirrored from `https://ftp.gnu.org/gnu/m4/m4-1.4.19.tar.xz`
* [ncurses-6.5.tar.gz](https://astral-sh.github.io/mirror/files/ncurses-6.5.tar.gz)
  * mirrored from `https://ftp.gnu.org/pub/gnu/ncurses/ncurses-6.5.tar.gz`
* [nasm-2.16.03-win64.zip](https://astral-sh.github.io/mirror/files/nasm-2.16.03-win64.zip)
  * mirrored from `https://www.nasm.us/pub/nasm/releasebuilds/2.16.03/win64/nasm-2.16.03-win64.zip`
* [readline-8.2.tar.gz](https://astral-sh.github.io/mirror/files/readline-8.2.tar.gz)
  * mirrored from `https://ftp.gnu.org/gnu/readline/readline-8.2.tar.gz`

On public availability
===

While this mirror is publicly accessible, it is intended for internal use by Astral's own CI
builds. Adding files here is at the discretion of the Astral team for the benefit of Astral
projects, and there is no SLA or expectation of future availability for non-Astral users. (For
instance, we might choose to change the hosting service to something other than GitHub Pages, and
we will only coordinate with Astral projects around the change in URLs.)

We also do not make any statements about the correctness, security, etc.  of the mirrored software,
other than that the files match the original copy. In particular, we _will_ retain files with known
vulnerabilities to avoid breaking older builds.

Maintenance
===

Add a file to `files/`, add it to the list above, and push.

Older branches/commits of our software should continue to be buildable as much as practical, so
please only _add_ new files and do not remove files just because they are outdated. (The only
reasons to remove files should be legal issues with redistribution or repository size limits. Note
that resolving either of these would likely require a filter-branch and force-push.)

It's only really useful to mirror something here if we expect that transferring the load to GitHub
Pages is helpful. In particular, mirroring files that are already hosted on GitHub or on other
CDN-backed sources like PyPI probably do not need to be mirrored, unless we're worried about files
being deleted from the upstream source.

Also, in general, it's preferable to avoid repeated downloads in the first place, e.g. by leaning
on caching inside the CI configuration.

Copyrights and licenses
===

Please see the copyright statements and licenses contained in the individual mirrored artifacts.
