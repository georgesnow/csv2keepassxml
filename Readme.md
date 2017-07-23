# From CSV into KeePass 2 XML

This is a simple Ruby script that will convert any CSV file into an XML document
compatible with the KeePass 2 format.

```

$ ./csv2keepassxml --help
Usage: csv2keepassxml [options] <path>

NOTE: Column indexes are 1-based.

    -g, --group NUM                  Column index for categories
    -n, --notes NUM                  Column index for notes
    -p, --password NUM               Column index for passwords
    -t, --title NUM                  Column index for titles
    -u, --username NUM               Column index for usernames
    -U, --url NUM                    Column index for URLs
    -T, --tags NUM,NUM,...           Column index(es) for tags
        --tags-separator SEP         Tag separator (default: ';')
    -F, --custom-fields NUM,NUM,...  Column index(es) for custom fields
    -d, --dbname NAME                Name of the database
    -H, --[no-]header                Parse a CSV with/without header
    -M, --macoskeychain              Parse the output of CSVKeychain
    -h, --help                       Prints this help
    -v, --[no-]verbose               Be verbose
```

If your CSV does not contain some data (e.g., it does not have a column with
notes), simply leave out the corresponding option.

Option `-M` is specifically for importing CSV files generated by
[CSVKeychain](https://github.com/lifepillar/CSVKeychain). If you use `-M` you
do not need to specify any column mappings (except possibly for tags and custom
fields).

If you use macOS, the generated XML file may be imported by
[MacPass](https://github.com/mstarke/MacPass) (v0.6.2-alpha or later) or
[KeeWeb](https://keeweb.info).

[KyPass Companion](http://www.kyuran.be/software/kypass4mac/) for macOS has
a CSV importer.
