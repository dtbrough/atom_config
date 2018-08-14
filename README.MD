# Backup and restore of Atom config
This will backup the config `.json`, `.cson`, `.coffee`, `.less` files from the .atom folder. The `apm` command will also create a list of installed packages for reinstalling later rather than backing up. The packages folder can be large if many packages used.

## Backup
To backup packages run from the .atom install location:
```
apm list --installed --bare > packages.list
git add .
git commit -m "This is my message"
get push origin https://github.com/dtbrough/atom_config.git
```

## Restore
To reinstall packages run from the .atom install location:
```
git clone https://github.com/dtbrough/atom_config.git
mv atom_config/* .
rmdir atom_config
apm install `cat packages.list`
```
