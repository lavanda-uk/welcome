Setup
> brew install gpg

Generate key
 > gpg --full-generate-key (more detailed instructions: https://help.github.com/en/articles/generating-a-new-gpg-key)

List your keys
> gpg -k

Share your public with the team
> gpg --armor --export <KEY_ID> # gotten from last command

Add your public GPG key to this page
> https://github.com/lavanda-uk/guides/blob/master/gpg_keys.md

----------

Import a colleague's public key
 > Download from GH
 > gpg --import igor.gpg

----------

How to encrypt to send to a colleague
> gpg --output db.dump.gpg --encrypt --recipient igor@getlavanda.com db.dump

How to decrypt an gpg encrypted file aimed at you
> gpg --output db.dump --decrypt db.dump.gpg
