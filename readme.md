# Build and test

```bash
namcap PKGBUILD
namcap <package file name>.pkg.tar.xz
```

As you are writing the build() function, you will want to test your changes frequently to ensure there are no bugs. You can do this using the makepkg command in the directory containing the PKGBUILD file. With a properly formatted PKGBUILD, makepkg will create a package; with a broken or unfinished PKGBUILD, it will raise an error.

If makepkg finishes successfully, it will place a file named pkgname-pkgver.pkg.tar.xz in your working directory. This package can be installed with the pacman -U command. However, just because a package file was built does not imply that it is fully functional. It might conceivably contain only the directory and no files whatsoever if, for example, a prefix was specified improperly. You can use pacman's query functions to display a list of files contained in the package and the dependencies it requires with pacman -Qlp [package file] and pacman -Qip [package file] respectively.

If the package looks sane, then you are done! However, if you plan on releasing the PKGBUILD file, it is imperative that you check and double-check the contents of the depends array.

Also ensure that the package binaries actually run flawlessly! It is annoying to release a package that contains all necessary files, but crashes because of some obscure configuration option that does not quite work well with the rest of the system. If you are only going to compile packages for your own system, though, you do not need to worry too much about this quality assurance step, as you are the only person suffering from mistakes, after all.

[testing](https://wiki.archlinux.org/index.php/Creating_packages#Testing_the_PKGBUILD_and_package)
[submission](https://wiki.archlinux.org/index.php/AUR_submission_guidelines)


