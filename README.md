# Collection of .gitignore files

This is a collection of .gitignore files I find useful for assorted projects. There are other [larger, more comprehensive collections of .gitignore files](https://github.com/github/gitignore), but these are the .gitignore configurations _I_ use and find useful.

I have not made any effort to modularize them.


## composer-applications.gitignore

A .gitignore file for PHP applications using Composer. This tracks the composer.lock file [as recommended in Composer's documentation](https://getcomposer.org/doc/01-basic-usage.md#commit-your-composer-lock-file-to-version-control).


## composer-libraries.gitignore

.gitignore for PHP library projects using Composer. This _does not_ track the composer.lock file; Composer's documentation [does not make a recommendation one way or the other here](https://getcomposer.org/doc/02-libraries.md#lock-file), but library projects should try to keep their requirements minimal IMO.


## wordpress.gitignore

This is the .gitignore file I use for WordPress repositories. It has worked well so far for sites that have a custom theme but manage plugins through WordPress's usual built-in update mechanisms.

This is designed to _not_ track WordPress components that update themselves:

* You allow WordPress to self-update, or you update it from a third-party system;
* You then make a code update in your WordPress repository and push the update;
* The push does _not_ break the updates installed in the site.

Some WordPress shops try to track entire WordPress sites in Git. This does not work well. WordPress works better when treated as a "platform" for smaller, independent software projects. Each individual project (plugin, theme, or other) should be tracked in its own repository, but not tracked in the WordPress sites using them.

### Plugins

All plugins are ignored.

### Themes

Only the base WordPress themes are ignored. Custom themes with a built-in update mechanism may end up tracked here, which could cause complications.

### Cruft, WPEngine, etc.

Rules are included to ignore cruft added by operating systems, IDEs, utilities, and loggers, as well as filetypes that WPEngine doesn't support when pushing to their remotes.
