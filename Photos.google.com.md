# Photos.google.com

Info shown on the website.

- Description
- Date & time.  Timezone can be set and is applied compared to current time zone, but isn't shown otherwise.  It also does not appear to be read from the file.  Seconds are not editable nor are displayed.
- Filename  
- MegaPixels size, Image dimensions, file size
- Camera Make
- Camera Model
- Fstop
- ExposureTime
- FocalLength
- ISO
- GPS coordinates

The order in which tags are read is variable, possibly dependent upon the order they appear within the file.  Different tags may be read different order.

The only editable information is the Description, the Date/Time/Timezone, and the approximate location by name or address.  GPS coordinates are not accepted.



| Metadata Name | Tags read                                                    | Tags Written<br />(site cannot write tags but see note [1](#f1) ) |
| ------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Description   | IPTC:Caption-Abstract<br />XMP-dc:Description<br />XMP-tiff:ImageDescription<br />Ducky:Comment | n/a                                                          |
| Date          | EXIF:DateTimeOriginal<br />XMP:DateCreated<br />XMP:DateTimeOriginal<br />IPTC:DateCreated + IPTC:TimeCreated<br />EXIF:CreateDate<br />XMP:CreateDate<br />XMP:DateTimeDigitized<br />IPTC:DigitalCreationDate + IPTC:DigitalCreationTime<br />EXIF:ModifyDate<br />XMP:ModifyDate<br />GPS:GPSDateStamp + GPS:GPSTimeStamp<span id="f2"><sup>2</sup></span><br />System:FileModifyDate | n/a                                                          |
| Make          | EXIF:Make<br>XMP-tiff:Make                                   | n/a                                                          |
| Model         | EXIF:Model<br />XMP-tiff:Model                               | n/a                                                          |
| FNumber       | EXIF:FNumber<br />XMP-exif:FNumber<br />XMP-exif:ApertureValue<br>EXIF:MaxApertureValue<br>XMP-exif:MaxApertureValue | n/a                                                          |
| ExposureTime  | EXIF:ExposureTime<br />XMP-exif:ExposureTime<br>EXIF:ShutterSpeedValue<br>XMP-exif:ShutterSpeedValue | n/a                                                          |
| FocalLength   | EXIF:FocalLength<br />XMP-exif:FocalLength                   | n/a                                                          |
| ISO           | EXIF:ISO<br />XMP-exif:ISO                                   | n/a                                                          |
| GPSLatitude   | GPS:GPSLatitude + GPS:GPSLatitudeRef                         | n/a                                                          |
| GPSLongitude  | GPS:GPSLongitude+GPS:GPSLongitudeRef                         | n/a                                                          |
| Orientation   | EXIF:Orientation                                             | n/a                                                          |

<span id="f1">1</span> Data edited on website isn't saved into file when picture is downloaded. This data can be downloaded using [Google Takeout](https://takeout.google.com/settings/takeout) (select Google Phots) in the form of a JSON file for each image.  Exiftool can then be used to embed this data (see [this StackOverflow answer](https://stackoverflow.com/a/42914024/3525475).)

<span id="f2">2</span> Even though GPS time stamps are supposed to be UTC, Google Photos doesn't attempt to adjust to the proper time zone.



## Google Takeout

https://takeout.google.com/settings/takeout

Using Google Takeout, you can download your photos and any data you edited in Google Photos.  The images you download will not have had their metadata updated by what was entered in Google Photos.  That data will instead appear in a matching `.json` file.

- title (Title, original filename)
- description (Description, value entered for description)
- url (Url, direct URL to view image, WARNING, ignores privacy settings)
- imageViews (ImageViews)
- creationTime (Time file was uploaded)
  - timestamp (CreationTimeTimestamp, Epoch seconds UTC)
  - formatted (CreationTimeFormatted, Date format code: %b %d, %Y, %I:%M:%S %p UTC)
- modificationTime
  - timestamp (ModificationTimeTimestamp, Epoch seconds UTC)
  - formatted (ModificationTimeFormatted, Date format code: %b %d, %Y, %I:%M:%S %p UTC)
- geoData (Location entered on website)
  - latitude (GeoDataLatitude)
  - longitude (GeoDataLongitude)
  - laltitude (GeoDataAltitude)
  - latitudeSpan (GeoDataLatitudeSpan)
  - longitudeSpan (GeoDataExifLongitudeSpan)
- geoDataExif (original location per file exif)
  - latitude (GeoDataExifLatitude)
  - longitude (GeoDataExifLongitude)
  - laltitude (GeoDataExifAltitude)
  - latitudeSpan (GeoDataExifLatitudeSpan)
  - longitudeSpan (GeoDataExifLongitudeSpan)
- photoTakenTime
  - timestamp (PhotoTakenTimeTimestamp, Epoch seconds UTC)
  - formatted (PhotoTakenTimeFormatted, Date format code: %b %d, %Y, %I:%M:%S %p UTC)


The files will be sorted into folders by albums or by dates if not in an album.  There will be a `metadata.json` file for each folder with the following data (as of 2019-01-28).  The tag names that exiftool will read from that file follows in parentheses 

- albumData
  - title (AlbumDataTitle)
  - access (AlbumDataAccess)
  - location (AlbumDataLocation)
  - date
     - timestamp (AlbumDataDateTimestamp) (epoch seconds of the time UTC)
     - formatted (AlbumDataDateFormatted) (Date format code: %b %d, %Y, %I:%M:%S %p UTC)
  - geoData
     - latitude (AlbumDataGeoDataLatitude)
     - longitude(AlbumDataGeoDataLongitude)
     - altitude (AlbumDataGeoDataAltitude)
     - latitudeSpan (AlbumDataGeoDataLatitudeSpan)
     - longitudeSpan (AlbumDataGeoDataLongitudeSpan)