Build bitcore zcashd by yourself
------------------------

Assuming you have debian-based distro.

* `sudo apt-get install git build-essential pkg-config libc6-dev m4 g++-multilib autoconf libtool ncurses-dev unzip git python zlib1g-dev wget bsdmainutils automake`
* `git clone 'https://github.com/str4d/zcash.git'`
* `cd zcash && git checkout v1.0.0-bitcore-3` - this is important only for bitcore address index patches
* `./zcutil/build.sh -j$(nproc)` - and wait an hour or two

Voila, `zcasd` is in `./src`.

Running zcashd
--------------
You have to download parameters first.

* `./fetch_params`

Two large files, 1GB total, will be downloaded sloooowly into `~/.zcash-params/` (from amazon aws).

Now you can run `./zcashd` from src.

Also see the official guide - note that it does *not* install bitcore addressindex patches!

https://github.com/zcash/zcash/wiki/1.0-User-Guide
