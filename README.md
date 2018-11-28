# Rob0-Documentation

This repository contains the documentation pages of Rob0.
This documentation is displayed in the [rob0.io](https://rob0.io) web app and written using [Markdown](https://guides.github.com/features/mastering-markdown/).

## File mapping

The root of this repository is [console.rob0.io/doc](https://console.rob0.io/doc) and the markdown documents of this repository is mapped under this root.

```
/unity/tutorials/getting-started.md
Mapped to https://console.rob0.io/doc/unity/tutorials/gettings-started
```

The default document of a folder is `index.md` and will be displayed if the user get inside a folder.

```
/unity/tutorials/index.md
Mapped to https://console.rob0.io/doc/unity/tutorials
```

## Contextual widgets

To add more interactivity and context to the documentation you can add a contextual widget to your pages. These widgets are inserted with double curly-braces syntax.

```
If you want to add a new version to {{ProjectName}} you can click on the button

Here, "{{ProjectName}}" is replaced by the "ProjectName" contextual widget
```

### Available widgets

* **ApiKey** Show the Api key of the current project in a card

## Internationalization

**NOTE** : Internationalization isn't implemented yet. This paragraph normalize the format of files for multiple language for the future i18n features of Rob0.

Internationalization is handled by adding an [IETF language tag](https://en.wikipedia.org/wiki/IETF_language_tag) as an extention prefix.

By default, the doc pages must be written in english and without any language tag extention.

```
doc.md > doc.md in English
index.es.md > index.md in Spanish
unity.fr-CA.md > unity.md in Canadian French
getting-started.fr.md > gettings-started.md in French
```
