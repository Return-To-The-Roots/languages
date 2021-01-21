# Return To The Roots

Language files for s25client

## Importing translations from launchpad

- Checkout current master branch (`git checkout master && git pull origin`)
- Request export from launchpad (PO format): https://translations.launchpad.net/s25rttr/s25client/+export
- Put downloaded files into RTTR/languages overwriting existing ones
- IMPORTANT: Run `make -B translations` in the build directory of rttr so PO files get sorted. Check the diff that there are only minor changes/updates, no complete reordering.
- Commit and create a pull request with the change

## Updating po template (rttr.pot)

- Checkout current master branch
- Download and install poedit (https://poedit.net) >= 1.8.7
- Open `rttr.pot`
- Press "Update" or "Catalog"->"Update from sources"
- Save and commit
- Optional: Update po files of your language using poedit.
    - Open po file
    - Click "Catalog"->"Update from POT file" (`rttr.pot`)
    - Check and fix auto-translations
    - Remove unused translations (Validate, that they are actually unused)
    - Save
    - Run `make -B translations` in the build directory to have gettext sort the translations. Alternatively run `msgmerge --sort-output --no-wrap --quiet --update --backup=none <abspath-to-file>.po <abspath-to-rttr.pot>rttr.pot` on every po-file
    - commit
- Create a pull request with the change

## Updating/Changing po files (Translations)

1. Use poedit (https://poedit.net) to edit .po files and create a pull request
    - Checkout current master branch
    - Open po file of your language
    - Make any changes to the translations
    - Save and commit

2. Translate online via https://translations.launchpad.net/s25rttr (could take longer to get into release)   
You can drop us a hint on Discord (https://discord.gg/kyTQsSx) if you did a larger translation.
