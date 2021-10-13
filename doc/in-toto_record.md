## in-toto record

Creates a signed link metadata file in two steps, in order to provide
              evidence for supply chain steps that cannot be carried out by a single command

### Synopsis

Creates a signed link metadata file in two steps, in order to provide
evidence for supply chain steps that cannot be carried out by a single command
(for which ‘in-toto-run’ should be used). It returns a non-zero value on
failure and zero otherwise.

### Options

```
  -c, --cert string                 Path to a PEM formatted certificate that corresponds
                                    with the provided key.
  -e, --exclude stringArray         Path patterns to match paths that should not be recorded as 
                                    ‘materials’ or ‘products’. Passed patterns override patterns defined
                                    in environment variables or config files. See Config docs for details.
  -h, --help                        help for record
  -k, --key string                  Path to a private key file to sign the resulting link metadata.
                                    The keyid prefix is used as an infix for the link metadata filename,
                                    i.e. ‘<name>.<keyid prefix>.link’. See ‘–key-type’ for available
                                    formats. Passing one of ‘–key’ or ‘–gpg’ is required.
  -l, --lstrip-paths stringArray    Path prefixes used to left-strip artifact paths before storing
                                    them to the resulting link metadata. If multiple prefixes
                                    are specified, only a single prefix can match the path of
                                    any artifact and that is then left-stripped. All prefixes
                                    are checked to ensure none of them are a left substring
                                    of another.
  -d, --metadata-directory string   Directory to store link metadata (default "./")
  -n, --name string                 Name for the resulting link metadata file.
                                    It is also used to associate the link with a step defined
                                    in an in-toto layout.
      --normalize-line-endings      Enable line normalization in order to support different operating 
                                    systems. It is done by replacing all line separators with a new 
                                    line character. Current iteration does not work since it led to
                                    altered byte segments in BLOBs.
```

### SEE ALSO

* [in-toto](in-toto.md)	 - Framework to secure integrity of software supply chains
* [in-toto record start](in-toto_record_start.md)	 - Creates a preliminary link file recording the paths and hashes of the
passed materials and signs it with the passed functionary’s key.
* [in-toto record stop](in-toto_record_stop.md)	 - Records and adds the paths and hashes of the passed products to the link metadata file and updates the signature.

