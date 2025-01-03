# yocto_useful_cmd
List of useful command for Yocto build.

Yocto use receipe file and bitbake tool to manage package and build process

# Setup environment
```
cd $SOURCE/poky
source build/conf/set_bb_env.sh
```

# Build full system
`bitbake machine-image`

Or we can use builtin convenience commands for building images:

Ex:
```
build-9607-image
build-9607-perf-image
```

# Clean all
`rm -rf tmp-glibc/ sstate-cache/`

# List all packages
`bitbake-layers show-recipes`

# Build package standalone
`bitbake <package-name>`

# Clean package standalone
`bitbake -c clean <package-name>`

Or use `cleansstate` to invalidate cache additional
`bitbake -c cleansstate <package-name>`

Or use `cleanall` is like cleansstate and refech source additional
`bitbake -c cleanall <package-name>`

# Rebuild package standalone
```
bitbake -c cleansstate <package-name>
bitbake <package-name>
```

# Rebuild kernel
`bitbake -c cleansstate virtual/kernel; bitbake virtual/kernel`

# Make menuconfig in Yocto
```
bitbake -c cleansstate virtual/kernel
bitbake virtual/kernel -c menuconfig
```
