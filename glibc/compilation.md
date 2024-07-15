```git clone https://github.com/fr0ster/glibc-all-in-one/```
```$ ./update_list```
```$ cat list```
```$ cat old_list```
`$ ./download 2.39-0ubuntu9_amd64` or `./download_old 2.34-0ubuntu3_amd64`
```$ cd libs/2.34-0ubuntu3_amd64/
$ ls
ld-linux-x86-64.so.2    libm.so.6           libpcprofile.so
libanl.so.1             libmvec.so.1        libpthread.so.0
libBrokenLocale.so.1    libnsl.so.1         libresolv.so.2
libc_malloc_debug.so.0  libnss_compat.so.2  librt.so.1
libc.so.6               libnss_dns.so.2     libSegFault.so
libdl.so.2              libnss_files.so.2   libthread_db.so.1
libmemusage.so          libnss_hesiod.so.2  libutil.so.1
```
```$ cd .debug```
- Para copiar los símbolos:
```$ sudo cp -R .build-id/. /usr/lib/debug/.build-id/.```
