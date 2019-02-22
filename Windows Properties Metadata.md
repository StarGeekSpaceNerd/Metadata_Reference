# Windows Properties Metadata

<!-- toc -->

## Jpeg

| Windows property | Tags Read                                                    | Tags Written                                                 |
| ---------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Title            | XMP:Title<br />EXIF:ImageDescription<br /><br />IPTC:Caption-Abstract<br />XMP:Description<br />EXIF:XPTitle | EXIF:ImageDescription<br/>EXIF:XPTitle<br />
IPTC:Caption-Abstract<br />
XMP:Description<br />
XMP:Title |
| Subject          | EXIF:ImageDescription<br/>EXIF:XPSubject                     | EXIF:XPSubject                                               |
| Rating           |                                                              |                                                              |

## Tiff

| Windows property           | Tags Read                                                    | Tags Written                                                 |
| -------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Title                      | XMP:Title<br/>EXIF:ImageDescription<br />XMP:Description<br />IPTC:Caption-Abstract<br />EXIF:XPTitle | EXIF:ImageDescription<br />EXIF:XPTitle<br />XMP-dc:Description<br />XMP-dc:Title<br />IPTC:Caption-Abstract <sup>[1](#f1)<sup> |
| Subject                    | EXIF:ImageDescription<br/>EXIF:XPSubject                     | EXIF:XPSubject                                               |
| Rating                     | EXIF:Rating<br/>EXIF:RatingPercent<br />XMP:Rating<br />XMP:RatingPercent | EXIF:Rating<br/>EXIF:RatingPercent<br />XMP-xmp:Rating<br />XMP-microsoft:RatingPercent |
| Tags                       | Combines all entries<br />EXIF:XPKeywords<br/>IPTC:Keywords<br />XMP:Subject | EXIF:XPKeywords<br />XMP-dc:Subject                          |
| Comments                   |                                                              | EXIF:XPComment                                               |
| Authors                    |                                                              | EXIF:Artist<br />EXIF:XPAuthor<br />XMP-dc:Creator           |
| Date taken                 |                                                              | EXIF:CreateDate<br />EXIF:DateTimeOriginal<br />XMP-xmp:CreateDate<br />EXIF:SubSecTimeDigitized<br/>EXIF:SubSecTimeOriginal |
| Program name               |                                                              | N/A                                                          |
| Date acquired              |                                                              | XMP-microsoft:DateAcquired                                   |
| Copyright                  |                                                              | EXIF:Copyright<br />XMP-dc:Rights                            |
| Camera maker               |                                                              | EXIF:Make                                                    |
| Camera model               |                                                              | EXIF:Model                                                   |
| F-stop                     |                                                              | N/A                                                          |
| Exposure time              |                                                              | N/A                                                          |
| ISO speed                  |                                                              | EXIF:ISO                                                     |
| Exposure bias              |                                                              | N/A                                                          |
| Focal length               |                                                              | N/A                                                          |
| Max aperture               |                                                              | N/A                                                          |
| Metering mode              |                                                              | EXIF:MeteringMode                                            |
| Subject distance           |                                                              | N/A                                                          |
| Flash mode                 |                                                              | EXIF:Flash                                                   |
| Flash energy               |                                                              | N/A                                                          |
| 35mm focal length          |                                                              | EXIF:FocalLengthIn35mmFormat                                 |
| Lens maker                 |                                                              | XMP-microsoft:LensManufacturer                               |
| Lens model                 |                                                              | XMP-microsoft:LensModel                                      |
| Flash maker                |                                                              | XMP-microsoft:FlashManufacturer                              |
| Flash model                |                                                              | XMP-microsoft:FlashModel                                     |
| Camera serial number       |                                                              | XMP-microsoft:CameraSerialNumber                             |
| Contrast                   |                                                              | EXIF:Contrast                                                |
| Brightness                 |                                                              | N/A                                                          |
| Light source               |                                                              | EXIF:LightSource                                             |
| Exposure program           |                                                              | EXIF:ExposureProgram                                         |
| Saturation                 |                                                              | EXIF:Saturation                                              |
| Sharpness                  |                                                              | EXIF:Sharpness                                               |
| White balance              |                                                              | EXIF:WhiteBalance                                            |
| Photometric interpretation | EXIF:PhotometricInterpretation                               | N/A                                                          |
| Digital zoom               |                                                              | N/A                                                          |
| EXIF version               |                                                              | ?                                                            |

## Png

| Windows property | Tags Read        | Tags Written     |
| ---------------- | ---------------- | ---------------- |
| Date taken       | PNG:CreationTime | PNG:CreationTime |

## MP4

| Windows property | Tags Read                                                    | Tags Written |
| ---------------- | ------------------------------------------------------------ | ------------ |
| Title            | XMP:Title EXIF:ImageDescription  IPTC:Caption-Abstract XMP:Description EXIF:XPTitle |              |
|                  |                                                              |              |
|                  |                                                              |              |

### Notes:

<span id="f1">1</span>: IPTC Data will be read, but it is update only.  If the IPTC entry does not previously exist, it will not be created.



- Date Taken - When setting through Windows, only the date appears to be editable.  The time will be the the current time
- Title - The priority that windows fills this tag is different for jpegs and tifs.
- IPTC Data written - Preliminary testing seems to indicate that these tags are not created by default.  I still need to test whether the tag or just the IPTC block needs to exist.
- RatingPercent - 
  - Writing
    - 5 Stars = 99
    - 4 stars = 75
    - 3 stars = 50
    - 2 stars = 25
    - 1 star = 1
    - 0 stars = removes tags
  - Reading
    - 88-100+ = 5 Stars
    - 63-87 = 4 stars
    - 38-62 = 3 stars
    - 13-37 = 2 stars
    - 1-12 = 1 star
    - no tag or 0 = 0 star
- PNG - The only property that Windows will fill for PNG files is Date Taken

### Revisions:

- 2015-07-25: Reorganized post, reformatted as table, added Tags, Ratings, Comment, Author, Program Name, Date Acquired, and Copyright for jpegs, added Title for Tif, added notes
- 2015-07-26: Resorted by order tags appear in windows Property->Details tab, fixed Rating, Author, Date Taken for jpeg, added Subject, Rating, Tags, Comments, Authors, Date Taken for Tif
- 2016-5-28: Updated info on Comments
- 2016-8-24: Updated info on Comments

### Reference:

- [Exiftool forum thread](http://u88.n24.queensu.ca/exiftool/forum/index.php/topic,6591.msg32875.html#msg32875)

### Credits:

deb27 - [Subject property for Windows 7](http://u88.n24.queensu.ca/exiftool/forum/index.php/topic,6589.msg32863.html#msg32863)
lewisn - [updated comment info](http://u88.n24.queensu.ca/exiftool/forum/index.php/topic,6591.msg38109.html#msg38109)