# Pihole Adlist/Blocklist Converter

A simple script for converting Adblock formatted lists into a domains-only block list compatible with pihole v4.3.2+, which no longer supports Adblock list styles: https://pi-hole.net/2019/09/21/pi-hole-4-3-2-release-notes/#page-content.

The script will parse all lines in the Adblock list format and extract all complete domains/hostnames (non-regex/wildcarded) into a plain-text list under `/filters` directory. Feel free to fork this repositry to manage your own collection of blocklists for pihole gravity.

## How to Use

Like pihole gravity, the script will only accept **text/plain** content type data. 

To run:
```
python3 adlist_converter.py <url>
```

For example:
```
python3 adlist_converter.py "https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/badware.txt"
```

### Notes:

- Some Adblock lists will include benign domains such as youtube[.]com, which the script will not ignore. Be cautious when adding full domains lists to pihole gravity. Scan the parsed blocklist for common domains before uploading. 
