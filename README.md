Metadata Reference
==================

## Photos.google.com

Info shown on website.
- Description
- Date & time.  Timezone can be set and is applied compared to current time zone, but isn't shown otherwise
- Filename without extension 
- MegaPixels size, Image dimensions, file size
- Camera Make
- Fstop
- ExposureTime
- FocalLength
- ISO
- GPS coordinates
  

| Metadata Name | Tags read<br />priority order                                | Tags Written<br />(site cannot write tags but see note [[1]](#f1) ) |
| ------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Description   | XMP-tiff:ImageDescription<br /> XMP-dc:Description<br />IPTC:Caption-Abstract<br />Ducky:Comment | n/a                                                          |
| Date          | (Timezone in timestamp ignored in favor of GPS coord or local TZ)<br /> IPTC:DateCreated+IPTC:TimeCreated<br />EXIF:DateTimeOriginal<br />XMP-photoshop:DateCreated<br />XMP-exif:DateTimeOriginal<br />IPTC:DigitalCreationDate+IPTC:DigitalCreationTime<br />EXIF:CreateDate<br />XMP-xmp:CreateDate<br />XMP-exif:DateTimeDigitized<br />EXIF:ModifyDate<br />XMP-xmp:ModifyDate<br />GPS:GPSDateStamp+GPS:GPSTimeStamp (adjusted for local timezone)<br />System:FileModifyDate<br /><br />-------------------- Rechecked 2018-05-01<br />EXIF:DateTimeOriginal<br />XMP:DateCreated<br />XMP:DateTimeOriginal<br />IPTC:DateCreated + IPTC:TimeCreated<br />EXIF:CreateDate<br />XMP:CreateDate<br />XMP:DateTimeDigitized<br />IPTC:DigitalCreationDate + IPTC:DigitalCreationTime<br />EXIF:ModifyDate<br />XMP:ModifyDate<br />GPS:GPSDateStamp + GPS:GPSTimeStamp (does not adjust to local time zone)<br />System:FileModifyDate | n/a                                                          |
| Model         | EXIF:Model<br />XMP-tiff:Model                               | n/a                                                          |
| FNumber       | EXIF:FNumber<br />XMP-exif:FNumber<br />XMP-exif:ApertureValue | n/a                                                          |
| ExposureTime  | EXIF:ExposureTime<br />XMP-exif:ExposureTime                 | n/a                                                          |
| FocalLength   | EXIF:FocalLength<br />XMP-exif:FocalLength                   | n/a                                                          |
| ISO           | EXIF:ISO<br />XMP-exif:ISO                                   | n/a                                                          |
| GPSLatitude   | GPS:GPSLatitude + GPS:GPSLatitudeRef                         | n/a                                                          |
| GPSLongitude  | GPS:GPSLongitude+GPS:GPSLongitudeRef                         | n/a                                                          |
| Orientation   | EXIF:Orientation                                             | n/a                                                          |

<span id="f1">1</span> Data edited on website isn't saved into file when picture is downloaded. This data can be downloaded using [Google Takeout](https://takeout.google.com/settings/takeout) (select Google Phots) in the form of a JSON file for each image.  Exiftool can then be used to embed this data (see [this StackOverflow answer](https://stackoverflow.com/a/42914024/3525475).)