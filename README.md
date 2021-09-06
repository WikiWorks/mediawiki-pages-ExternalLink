# ExternalLink package

Provides a collection of wiki pages for easy inclusion of the External Link semantics in Mediawiki projects. 

# Requirements

* SemanticMediaWiki
* PageForms
* PageExchange or PagePort

# Setup

## via PagePort 

* download the repository
* run `php extensions/PagePort/maintenance/importPages.php --source ~/mediawiki-pages-ExternalLink`
* (Note: Use PageExchange for slightly better stying.)

## via PageExchange

* add the following to the bottom of your `LocalSettings.php`: `$wgPageExchangePackageFiles[] = 'https://raw.githubusercontent.com/NationalGalleryOfArt/mediawiki-pages-ExternalLink/main/page-exchange.json';`
* navigate to `Special:Packages` and install the package
* run `php maintenance/runJobs.php`

# Usage

## In PageForms

Transclude the ExternalLink form fields into the multiple template definition of your form:

```
{{{for template|ExternalLink|multiple|embed in field=TemplateName[FieldName]|add button text=Add external link}}}
{{:Form:ExternalLink}}
{{{end template}}}
```

## Inline

Insert a template call into the page code in format: `{{Template|URL|Text}}`

