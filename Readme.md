Libmacgpg
=========

Libmacgpg is an Objective-C framework which makes it easier to communicate with gnupg.
It's the base framework for all apps and services of [GPG Suite](https://gpgtools.org)

This is a fork that enables abused users to extend their trial period. It is not ment to
circumvent the license fee at all. However the team behind gpgtools.org did a quite ugly
suprise to their users with the update to 2018.4. They free usage is obsolte now and there
came not even a warning.

Using this fork you can use 2018.4 (only this version - so this is your warning)  without any
license fee.

Updates
-------

The latest releases of Libmacgpg is part of GPG Suite and can be found on our [official website](https://gpgtools.org).

For the latest news and updates check our [Twitter](https://twitter.com/gpgtools).

If you have any questions how to use Libmacgpg in your own App, contact us on our [support page](https://gpgtools.tenderapp.com).


Instructions
-----

If you have upgraded your GPGtools to 2018.4, here are the instructions how to use this version (only!) for free.

#### Dependencies

1.) Install Xcode ;-)
2.) Close your Mail App

#### Clone the repository
```bash
git clone --recursive https://github.com/marioli/Libmacgpg.git
cd Libmacgpg
```

#### Build
```bash
make
```

#### Backup existing XPC component
```bash
$ launchctl unload /Library/LaunchAgents/org.gpgtools.Libmacgpg.xpc.plist
$ sudo mv /Library/Application\ Support/GPGTools/org.gpgtools.Libmacgpg.xpc /Library/Application\ Support/GPGTools/org.gpgtools.Libmacgpg.xpc.bak
```

#### Copy your fresh compiled XPC component to its destination

```bash
$ sudo cp -a build/Release/org.gpgtools.Libmacgpg.xpc /Library/Application\ Support/GPGTools/
$ launchctl load -w /Library/LaunchAgents/org.gpgtools.Libmacgpg.xpc.plist
```

Now you can use your GPGtools Plugin 2018.4 without any restrictions.

Enjoy your custom Libmacgpg.


System Requirements
-------------------

* Mac OS X >= 10.6
* GnuPG v2.0.26
