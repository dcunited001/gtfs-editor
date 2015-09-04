gtfs-editor
===========

A web-based GTFS editing framework.

*Requires*

	Play Framework 1.2.x (does not work with Play 2.x)
	Postgresql 9.1+ 
	PostGIS 1.5+

*Install*

Follow the instructions [here](INSTALL.md) for information on installation.

### Getting Play 1.x set up within Jetbrains

Follow [these instructions](https://www.jetbrains.com/idea/help/play-framework-1-x.html) to set up the workspace file and add run/debug environments.

### Uploading GTFS for Roanoke

#### [Download](http://www.gtfs-data-exchange.com/agency/valley-metro/) and Unzip GTFS

```shell
unzip roanoke-va-us.zip -d roanoke-va-us
```

#### Remove UTF-8 Byte Order Mark from files

```shell
cd roanoke-va-us
sed -i -e '1s/^\xef\xbb\xbf//' *
```

#### Rezip and Upload

```shell
### must be within the folder for the files to be indexed properly
cd roanoke-va-us
zip -r -X ../roanoke.zip *
```

### Notes

- GTFS uploads all data, but some of the connections between models seem to be invalid.
- All routes are marked "In Progress"
- Fares are parsed, but not uploaded and must be included when uploading the data to google.