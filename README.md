# Custom Page Headers Symphony Extension

- Version: 1.1
- Author: Henry Singleton
- Build Date: 11 Apr 2012
- Requirements: Symphony 2.2.5 - Symphony 2.3.x

## Overview

This Symphony CMS extension allows you to define headers by page output. This lets you build headers using data from datasources or other page information. Anything that's accessible from a standard page really!

Great for generating redirect urls for 301/302 redirects if you need information from existing Symphony entries, or want to store redirect stats via an event etc. 

## Installation

1. Upload the 'page_headers' folder in this archive to your Symphony 'extensions' folder.

2. Enable it by selecting the "Page Headers" extension, choose Enable from the with-selected menu, then click Apply.

## Usage

- Create a new page, and give it a page type of 'headers'.
- Make the page output plain text that you want for your headers. If you also want to output actual page content in the message body, simply separate your headers by a blank newline (as per the HTTP spec for separating message headers/body).

## Notes

If HTML/XML is detected at the start of the page output, the extension will not do anything, even if the 'headers' page type is set.

## Example

Create a new page, give it a page type of 'headers' and save the following as the page template content:

	<?xml version="1.0" encoding="UTF-8"?>
	<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
	
	<xsl:output method="xml"
		omit-xml-declaration="yes"
		encoding="UTF-8"
		indent="yes" />
	
	<xsl:template match="/">
		HTTP/1.1 301 Moved Permanently
		Location: http://www.google.com/
	</xsl:template>
	
	</xsl:stylesheet>

## Changelog

- **1.0** Initial release for internal project.
- **1.1** Updated extension.meta.xml to include namespace for Symphony 2.3 compatibility. (Thanks to andrewminton)
