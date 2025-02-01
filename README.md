# fanwikis/Description2

This is a fork of the MediaWiki Description2 extension maintained by the fanwikis.org Team with tweaks and improvements for use on fanwikis.org's MediaWiki installation.

## Changes

### Removing `<style>` tags

When using the TemplateStyles extension at the top of an article, the Description may end up being just CSS. This is not what we want, so we remove the `<style>` tags from the description.

```diff
- $pattern = '%<table\b[^>]*+>(?:(?R)|[^<]*+(?:(?!</?table\b)<[^<]*+)*+)*+</table>%i';
+ $pattern = '%<(table|style)\b[^>]*+>(?:(?R)|[^<]*+(?:(?!</?(table|style)\b)<[^<]*+)*+)*+</(table|style)>%i';
```
