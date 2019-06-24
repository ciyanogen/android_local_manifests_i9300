LineageOS
===========

How to Build?
-------------

To initialize a shallow clone, which will save even more space & time, use a command like this:

```bash
  mkdir lineage
  cd lineage
  repo init git://github.com/LineageOS/android.git -b lineage-15.1 --depth=1
```

Clone my repo:
----------------

```bash
git clone https://github.com/ciyanogen/android_local_manifests_i9300 -b lineage-15.1-custom .repo/local_manifests
``` 

Then to sync up:
----------------

```bash
  repo sync -c -f --force-sync --no-clone-bundle --no-tags -j64
```

Finally to build:
-----------------
From root directory of Project, perform following commands in terminal

```bash
git clone https://github.com/ciyanogen/android_local_manifests_i9300 -b lineage-15.1-custom
. build/envsetup.sh
bash android_local_manifests_i9300/fetch.sh
bash android_local_manifests_i9300/apply.sh
```

Altering the subject line to reflect your information:
```bash
subject='/C=US/ST=California/L=Mountain View/O=Android/OU=Android/CN=Android/emailAddress=android@android.com'
mkdir .android-certs
for x in releasekey platform shared media testkey; do \
    ./development/tools/make_key .android-certs/$x "$subject"; \
done
```

```bash
  . build/envsetup.sh
  lunch lineage_i9300-userdebug
  make -jX bacon
```
