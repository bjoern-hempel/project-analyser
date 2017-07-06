# A project analyser

A project analyser that tries to detect the application type and version number from given web directory.

### A.1) installation

This application uses the friends of bash libraries (https://github.com/bjoern-hempel/friends-of-bash). Check that the libraries are available:

```
user$ friends-of-bash --version
friends-of-bash/v0.0.11
```

If you can see a similar friends of bash version output like above, you can now install this application:

```
user$ sudo -E friends-of-bash install "git@github.com:bjoern-hempel/project-analyser.git"
```

If you don't have installed the friends of bash libraries, please install them first. In short:

```
user$ cd ~ && git clone git@github.com:bjoern-hempel/friends-of-bash.git && cd friends-of-bash
user$ sudo -E bin/install
user$ cd .. && rm -rf friends-of-bash
```

## 1.) Usage

### 1.1) Show the help dialog (`--help`)

```
user$ project-analyser --help

A project analyser by Björn Hempel <bjoern@hempel.li>

Usage: bin/project-analyser [options...] [<path>]
 -h,    --help                    Shows this help.
 -v,    --version                 Shows the version number.
```

### 1.2) Simply return the app type, version number, file size and count

```
user$ project-analyser /var/www/de/[domain]/[subdomain]/wordpress/html
app:        Wordpress
version:    4.7.5
size:       212M
file-count: 3910
```

### 1.3) Only show the application name (`--show-only-app-name`)

```
user$ project-analyser /var/www/de/[domain]/[subdomain]/wordpress/html --show-only-app-name
Wordpress
```

### 1.4) Also try to analyse the virtual hosts (`--analyse-virtual-hosts`)

ATTENTION: This process needs admin rights!

```
user$ sudo project-analyser /var/www/de/[domain]/[subdomain]/wordpress/html --analyse-virtual-hosts
servername: wordpress.[subdomain].[domain].de
app:        Wordpress
version:    4.7.5
size:       212M
file-count: 3910
```

## B.) License

MIT © [Björn Hempel](https://www.ixno.de/project-analyser)

Have fun! :)
