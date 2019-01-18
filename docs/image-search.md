# Image Search Parameters

The API has endpoints for querying our data in which you can use free text search together with one or more of the following filters:

### ip: (string) 
Search by IP address or CIDR. 

    e.g ip:"192.168.1.1/24" or ip:192.168.1.1

### port: (int) 
Search by port number. 
    
    e.g. port:80

### country: (string) 
Search using ISO2 Country Codes. 
    
    e.g. country:ES

### geoip.country_name: (string) 
Search using country names. 
    
    e.g. geoip.country_name:spain

### geoip.city_name: (string) 
Search using city names. 
    
    e.g. geoip.city_name:madrid

### asn: (int)
Search by ASN. 

    e.g. asn:4812

### tags: (string)
Search by tags. Can be mobile, rdp, vnc, windows, x11.

    e.g. tags:mobile

### words: (string)
Search by words found by OCR.

    e.g. words:alarm

### has_faces: (boolean)
Search for images with faces detected.

    e.g. has_faces:true

### height: (int)
Search by image height (supports ranges).

    e.g. height:1024

### width: (int)
Search by image width (supports ranges).

    e.g. width:768

### ts: (date)
Search by timestamp.

    e.g. ts:[2018-09-01 TO 2018-10-01]


## Notes

**Free Text**: not specifying a field will search on the full records, which can include other information not stated above.

**Conditionals**: the following conditionals are available: NOT, AND, OR. Must be UPPERCASE.

**String fields caveat**: if the string is expected to have spaces or some kind of punctuation in the middle, instead of querying _field:value_ try instead _field.keyword:"value"_. The first one will search for any occurrence of any of the words in _value_, while the second one will search for an exact match of the string.