# pymergedup
find files with duplicate content

You have seen a few of these scripts, I have written a few of these scripts -- find duplicated files when they have
the same size, and go through all of them to find if they have a maching hash.

The main differences:
- with minimal dependencies (Python 2.7 only)
- don't go through ALL the files checking their sha256 - this makes it very slow if you have lots of different files with similar sizes (dashcam outputs, filesystem images).  Instead, check their first few bytes first to see if they match (if there is a possible match, of course check the hash of the full contents)
- output the duplicates in a way that helps to replace them with hardlinks (i.e. shell ln commands)
