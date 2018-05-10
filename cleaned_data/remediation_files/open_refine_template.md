# Open Refine Template for Howard Baker Speech Transcripts


## Template

#### Prefix

```
<?xml version="1.0" encoding="UTF-8"?>
<modsCollection xmlns="http://www.loc.gov/mods/v3" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xlink="http://www.w3.org/1999/xlink" xsi:schemaLocation="http://www.loc.gov/mods/v3 http://www.loc.gov/standards/mods/v3/mods-3-5.xsd">
```
####Body

```
<mods>
<identifier type="local">{{cells["identifier_adminDB"].value}}</identifier>
{{if(isBlank(cells["title"].value),'', '<titleInfo><title>' + cells['title'].value + '</title></titleInfo>')}}
{{if(isBlank(cells["title_supplied"].value),'', '<titleInfo supplied="yes"><title>' + cells['title_supplied'].value + '</title></titleInfo>')}}
<abstract>{{cells['abstract'].value}}</abstract>
<originInfo>
{{if(isBlank(cells['date_of_speech'].value), '', '<dateCreated>' + cells['date_of_speech'].value + '</dateCreated><dateCreated encoding="edtf" keyDate="yes">' + cells['date_of_speech_edtf'].value + '</dateCreated>')}}
{{if(isBlank(cells['date_questionable'].value), '', '<dateCreated qualifier="questionable">' + cells['date_questionable'].value + '</dateCreated><dateCreated qualifier="questionable" encoding="edtf" keyDate="yes">' + cells['date_questionable_edtf'].value + '</dateCreated>')}}
{{if(isBlank(cells['date_approximate'].value), '', '<dateCreated qualifier="approximate">' + cells['date_approximate'].value + '</dateCreated>' + if(isBlank(cells['date_approximate_edtf'].value), '', '<dateCreated qualifier="approximate" encoding="edtf" keyDate="yes">' + cells['date_approximate_edtf'].value + '</dateCreated>') + if(isBlank(cells['date_approximate_start'].value), '', '<dateCreated qualifier="approximate" encoding="edtf" keyDate="yes" point="start">' + cells['date_approximate_start'].value + '</dateCreated><dateCreated qualifier="approximate" encoding="edtf" keyDate="yes" point="end">' + cells['date_approximate_end'].value + '</dateCreated>'))}}
{{if(isBlank(cells['location_of_speech'].value), '', '<place><placeTerm' + if(isBlank(cells['location_URI'].value), '', ' valueURI="' + cells['location_URI'].value + '"') + '>' + cells['location_of_speech'].value + '</placeTerm></place>')}}
</originInfo>
{{'<physicalDescription>' + '<extent>' + cells['extent'].value + '</extent><form authority="aat" valueURI="' + cells['form_URI'].value + '">' + cells['form'].value + '</form>' + '<internetMediaType>image/jpeg</internetMediaType><digitalOrigin>reformatted digital</digitalOrigin></physicalDescription>'}}
{{if(isBlank(cells['subject_topic_LCSH'].value), '', '<subject authority="lcsh" valueURI="' + cells['LCSH_URI'].value + '"><topic>' + cells['subject_topic_LCSH'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject_topic_LCSH2'].value), '', '<subject authority="lcsh" valueURI="' + cells['LCSH2_URI'].value + '"><topic>' + cells['subject_topic_LCSH2'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject_topic_LCSH3'].value), '', '<subject authority="lcsh" valueURI="' + cells['LCSH3_URI'].value + '"><topic>' + cells['subject_topic_LCSH3'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject_topic_LCSH4'].value), '', '<subject authority="lcsh" valueURI="' + cells['LCSH4_URI'].value + '"><topic>' + cells['subject_topic_LCSH4'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject_topic_LCSH5'].value), '', '<subject authority="lcsh" valueURI="' + cells['LCSH5_URI'].value + '"><topic>' + cells['subject_topic_LCSH5'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject_geographic_LC1'].value), '', '<subject authority="lcsh" valueURI="' + cells['geographic_LC1_URI'].value + '"><geographic>' + cells['subject_geographic_LC1'].value + '</geographic></subject>')}}
{{if(isBlank(cells['subject_geographic_LC2'].value), '', '<subject authority="lcsh" valueURI="' + cells['geographic_LC2_URI'].value + '"><geographic>' + cells['subject_geographic_LC2'].value + '</geographic></subject>')}}
{{if(isBlank(cells['subject_geographic_LCSH'].value), '', '<subject authority="lcsh" valueURI="' + cells['geographic_LCSH_URI'].value + '"><geographic>' + cells['subject_geographic_LCSH'].value + '</geographic></subject>')}}
{{if(isBlank(cells['subject_geographic_LCSH2'].value), '', '<subject authority="lcsh" valueURI="' + cells['geographic_LCSH2_URI'].value + '"><geographic>' + cells['subject_geographic_LCSH2'].value + '</geographic></subject>')}}
{{if(isBlank(cells['subject_geographic_LCSH3'].value), '', '<subject authority="lcsh" valueURI="' + cells['geographic_LCSH3_URI'].value + '"><geographic>' + cells['subject_geographic_LCSH3'].value + '</geographic></subject>')}}
{{if(isBlank(cells['subject_name_NAF'].value), '', '<subject authority="naf" valueURI="' + cells['subject_name_NAF_URI'].value + '"><name><namePart>' + cells['subject_name_NAF'].value + '</namePart></name></subject>')}}
{{if(isBlank(cells['subject_name_NAF2'].value), '', '<subject authority="naf" valueURI="' + cells['subject_name_NAF2_URI'].value + '"><name><namePart>' + cells['subject_name_NAF2'].value + '</namePart></name></subject>')}}
{{if(isBlank(cells['name'].value), '', '<name valueURI="' + cells['name_URI'].value + '"><namePart>' + cells['name'].value + '</namePart>' + if(isBlank(cells['name'].value), '', '<role><roleTerm authority="marcrelator" valueURI="http://id.loc.gov/vocabulary/relators/aut">Author</roleTerm></role>') + '</name>')}}
<language><languageTerm type="text" authority="iso639-2b">{{cells['language'].value}}</languageTerm></language>
<relatedItem displayLabel="Project" type="host"><titleInfo><title>{{cells['digital_collection'].value}}</title></titleInfo></relatedItem>
<relatedItem displayLabel="Collection" type="host"><titleInfo><title>{{cells['collection'].value}}</title></titleInfo><identifier>{{cells['collection_identifier'].value}}</identifier><location><url>{{cells['ARK'].value}}</url></location></relatedItem>
<location><physicalLocation valueURI="http://id.loc.gov/authorities/names/no2014027633">University of Tennessee, Knoxville. Special Collections</physicalLocation></location>
<recordInfo><recordContentSource valueURI="http://id.loc.gov/authorities/names/n87808088">University of Tennessee, Knoxville. Libraries</recordContentSource><languageOfCataloging><languageTerm type="text" authority="iso639-2b">English</languageTerm></languageOfCataloging></recordInfo>
<accessCondition type="use and reproduction" xlink:href="{{cells['rights_URI'].value}}">{{cells['rights'].value}}</accessCondition>
</mods>

```

#### Suffix

```
</modsCollection>
```