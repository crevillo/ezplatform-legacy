# eZ Platform with Legacy

## What is eZ Platform with Legacy?
Are you one of those developers that still don't want to get ride of Legacy admin interface?
Since [this commit](https://github.com/ezsystems/ezplatform/commit/5a76be259697f308d93c666f75d2b1f808377846)
eZ Platform is not shipped with legacy-bridge anymore. So, if you still want to add legacy admin
interface and use all those old eZ Publish extensions, you need to adapt your installation following
the instructions given in the [legacy brige INSTALL.md file](https://github.com/ezsystems/LegacyBridge/blob/master/INSTALL.md)

eZ Platform with Legacy will just do this for you, allowing the installation of eZ Platform and old legacy
code without the need to manually modify anything.

## eZ Publish Community vs. this repo
The eZ Publish community is still available, but it does not contain last changes made to eZ Platform repo and so
 you won't get all the last updates eZ Platform has.
Oh the other side, eZ Platform with Legacy can be used with the last versions of eZ Platform.

### Abstract:
- **Very extensible** *You can extend the application and the content model in many ways*
- **Future & backwards compatible** *Strong BC policy on data as well as code*
- **Multi channel by design** *Strong focus on separation between <sup>semantic</sup> content & design*
- **Scalable** *Easily scale across multiple servers out of the box*
- **Future proof** *Architecture designed to allow even more content scalability and performance in the future*
- **Stable** *Built on experience building CMS since early 2000, and in production since 2012*
- **Integration friendly** *Numerous events and signals to hook into for advanced workflow needs*

### Main packages:
- **ezpublish-kernel** (building on top of **Symfony Framework**):
 - Content Repository with a highly flexible content model exposed via a Public API.<br>
   Out of the box powered by SQL *Storage Engine* using [Doctrine DBAL](http://doctrine-dbal.readthedocs.org/en/latest/reference/configuration.html#driver),
   data cache implementation using [Stash](http://www.stashphp.com/Drivers.html) and binary file system handled by [Flysystem](https://github.com/thephpleague/flysystem#adapters).
   Improved *Storage Engine* planned, custom implementation for increased data scalability already possible.
 - Powerful (& extensible) Content Query engine, currently powered by SQL, soon Solr/ElasticSearch
 - Very high performance thanks to content & user aware HTTP <sup>"view"</sup> cache (now [using](https://github.com/FriendsOfSymfony/FOSHttpCacheBundle))
 - Introduces concept of "web sites" allowing you to manage several within one installation
 - Allows to rapidly set up *Contextual override* of content display twig templates as well as controller based on Content type, section, and much more.
 - Helpers, services, events and signals allowing you to efficiently create everything from simple web sites to complex applications
- **PlatformUIBundle**: A modern, extensible "Backend" UI for managing content & administering the site

### Further information:
eZ Platform is 100% open source and is released as companion to a commercial *eZ Studio* software which adds advanced
features for editorial teams and media companies, 100% built on top of *eZ Platform* APIs.

- [eZ Publish 5.x Architecture, including "Platform Stack"](https://doc.ez.no/pages/viewpage.action?pageId=11403666)
- [eZ Studio and eZ Platform RoadMap](http://ez.no/Blog/What-to-Expect-from-eZ-Studio-and-eZ-Platform)
- [eZ Platform 2015 release plan](http://ez.no/Blog/What-Releases-to-Expect-from-eZ-in-2015)
- eZ Systems AS *(commercial products and services)*: [ez.no](http://ez.no/)
- eZ Community: [share.ez.no](http://ez.no/)

## Install
For installation instructions, see [INSTALL.md](https://github.com/crevillo/ezplatform-legacy/blob/master/INSTALL.md).

## Requirements
Full requirements can be found on the [Requirements](https://doc.ez.no/display/TECHDOC/Requirements) page.

*TL;DR: supported PHP versions are 5.5, 5.6 and 7.0 (for dev use), using mod_php or php-fpm, and either MySQL 5.5/5.6 or MariaDB 5.5/10.0.*

## Issue tracker
Submitting bugs, improvements and stories is possible on the issue tracker or this repo.

## LICENSE
http://www.gnu.org/licenses/gpl-2.0.txt GNU General Public License v2
