# ctf-prep

## Misc

```console
$ chmod 777 file.txt # Full permissions
$ mount file /mnt/dir # Mounting file
$ mount -o loop file /mnt/dir # Another mount option
$ xclip -sel c < input_file # Copy file to clipboard
$ sudo -l # List what can I do as sudo
$ unzip file.zip # Unzip zip file
$ tar -xvzf file.tar.gz # Unzip tar.gz file
$ gzip -dk file.gz # Unzip gz file
$ bzip2 -d filename.bz2 # Unzip bzip2
$ cpio -idv < file # Unzip cpio archives
$ ar -p file # Unzip current ar archives
$ lzip -dk file # Unzip lzip file
$ lz4 -dk flag flag.out # Unzip lz4 file
$ lzma -dk flag.lzma # Unzip lzma file
$ lzop -dk -o flag.out flag.lzop # Unzip lzop file
$ xz -dk flag.xz # Unzip xz file
$ compgen -ac # list available commands
$ echo "$(<a.txt )" # echo file contents
$ : ; echo "blabla" # : useless command
$ grep -r -E -o ".{0,10}wantedText.{0,10}" # grep 10 chars before and after
```

Vi can check directories as well.

Morse code - audacity.

[Regex](https://regexr.com/)

APK files can be unzipped.

APK dex files can be decompiled with [mobsf](https://github.com/MobSF/Mobile-Security-Framework-MobSF). Just enter mobsf into the terminal, then localhost:8000 and upload the APK.

## Crypto

Ceasars cipher - shift all letters by n.

ROT(n) - ceasars cipher. (https://www.dcode.fr/rot-cipher)

ROT13 - encrypt and decrypt the same way.

[Base64](https://www.base64decode.org/)

CTRL-A on text to see for hidden things. (or hexdump)

Whitespace (spaces and tabs) cipher - use [stegsnow](https://www.kali.org/tools/stegsnow/) or [snow](https://darkside.com.au/snow/)

Esoteric Programming Languages - if the text looks a bit strange, maybe it is a stupid programming language.

## Forensics

File type
```console
$ file tmp.txt
```

Metadata
```console
$ exiftool -a tmp.txt
```

File attributes
```console
$ getfattr -d tmp.txt
```

Embeded files
```console
$ binwalk tmp.txt
$ binwalk -e tmp.txt # to extract files
$ foremost tmp.txt
```

PDF's
```console
$ pdfinfo file.pdf
```

[Magic numbers](https://en.wikipedia.org/wiki/List_of_file_signatures)
[Stegsolve](https://github.com/zardus/ctf-tools/blob/master/stegsolve/install) - f.e. when you see a single color image.

File hexdump
```console
$ xxd file.png > tmp.txt
$ xxd -r tmp.txt > file2.png # Reverse
```

IMG file
```console
$ mmls image.img # Prints partitions
```

Hidden info in images
```console
$ steghide extract -sf file.jpg
$ zsteg file.png
```

LSB/MSB hiding (https://github.com/Pulho/sigBits)

## Net

Always check robots.txt

BurpSuite Proxy - to modify [http headers](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields). Like browser, country, reference website, and all custom data.

Cookies

Dirbuster - find files and directories

Web inspector

Wireshark - to see full info Right Click -> Follow -> (SMT) stream. CTRL+F find string (or hex, or bin) text that matches flag pattern. Extract files File->Object->Bam

[XXE](https://portswigger.net/web-security/xxe)

[SQL injection](https://www.w3schools.com/sql/sql_injection.asp)

[SQL common filter bypass](https://portswigger.net/support/sql-injection-bypassing-common-filters)

```
ad'||'min';#
```

[JSON Web Token attacks](https://www.invicti.com/blog/web-security/json-web-token-jwt-attacks-vulnerabilities/) - f.e. modify algorithm to None, change to admin and remove the signature, but leave both (2) seperators.

## Online tools

[CyberChef](https://gchq.github.io/CyberChef/)

[Number conversion](https://www.rapidtables.com/convert/number/hex-to-decimal.html)

[Type conversion](https://v2.cryptii.com/octal/text)

[quipqiup - auto substitution cypher solver](https://quipqiup.com/)

## Reverse Engineering

IDA64 for disassembling (F5 for c code)

[JD-GUI](https://java-decompiler.github.io/#jd-online) for disassembling JAVA

gdb
``` console
$ gdb ./file
$ disassemble main # info about main
$ b main # break at the start of main
$ step # do one by one steps untill exit from function
$ info registers # print register info
$ info registers eax # print eax register
```

UPX
``` console
$ upx -d file # unpacks upx compressed file
```

## Running stuff

``` console
$ python3 file.py # Python3 run
$ gcc main.c -o main # C compile
$ g++ main.cpp -o main # C++ compile
$ rustc main.rs # Rust compile
$ cargo build # Cargo Rust compile
```