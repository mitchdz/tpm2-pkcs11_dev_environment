## Host information

| OS     | Kernel |
| ----------- | ----- |
| Ubuntu 16.04.6  | 4.15.0-88-generic |

---

## software dependency versions

| stack     | version |
| ----------- | ----- |
| tpm2-abrmd  | 2.3.0 |
| tpm2-pkcs11 | 1.3.1 |
| tpm2-tools  | 4.1.3 |
| tpm2-tss    | 2.4.1 |
| gcc         | 9.3.0 |

to install the right version of gcc execute the following:

```
sudo apt install -y gcc-9
sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-9 30
```


**note**: you may encounter the following error during bootstrap:

`ERROR: ax_is_release.m4 is outdated. ./configure will fail.`

execute the following code to resolve the ERROR
```
wget http://ftpmirror.gnu.org/autoconf-archive/autoconf-archive-2019.01.06.tar.xz
tar -xvf autoconf-archive-2019.01.06.tar.xz
cp autoconf-archive-2019.01.06/m4/ax_code_coverage.m4 autoconf-archive-2019.01.06/m4/ax_prog_doxygen.m4 autoconf-archive-2019.01.06/m4/ax_is_release.m4 m4/
```
---

## tpm2-tss

Note: Currently issue persists

`/bin/bash: systemd-sysusers: command not found`

```
wget https://github.com/tpm2-software/tpm2-tss/archive/2.4.1.tar.gz
tar -xvzf 2.4.1.tar.gz
cd tpm2-tss-2.4.1/
./bootstrap
./configure
make -j$(nproc)
sudo make install
```

---




## tpm2-abrmd

```
sudo useradd --system --user-group tss
wget https://github.com/tpm2-software/tpm2-abrmd/archive/2.3.0.tar.gz
tar -xvzf 2.3.0.tar.gz
cd tpm2-abrmd-2.3.0/
```

---

## tpm2-tools
```
TODO:
```


## tpm2-pkcs11
```
TODO
```
