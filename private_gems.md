# Private Gems

We are introducing private gems

## option one: use https to bundle private gems

When you bundle lvdam, it will prompt you to insert the github password.

It just works if you already did this once, because it will be persisted in macos keychain.

(Suspicion: this option won't work for you if you have 2FA set up for Github)

## option two: set BUNDLE_GITHUB__COM

by setting env var BUNDLE_GITHUB__COM it will use the value of that env variable to bundle gems that are from a git source and located in a private github.com repo.

- locally: you can create a personal access token in github, and set
  this env variable at the console start .zshrc
- for heroku/circle ci: we use the env var and a personal token from the github bot user lavandaengineer

### Generating a private
<img width="1353" alt="Screenshot 2021-06-17 at 18 20 58" src="https://user-images.githubusercontent.com/2815199/122445351-623c5880-cf99-11eb-8064-7b2bad623a62.png">

<img width="922" alt="Screenshot 2021-06-17 at 18 22 28" src="https://user-images.githubusercontent.com/2815199/122445376-67010c80-cf99-11eb-8088-e18a8b9812d4.png">

Note: since we pull gems from private repos, you may need to actually grant "Full control of private repositories" (first checkbox).

then put the value in .zshrc (as long as it is not in git this file)
```
export BUNDLE_GITHUB__COM=x-access-token:THE_TOKEN_GENERATED_IN_THE_IMAGE
```

## option three: local copy of the gem


```
   pushd .. && (git clone git@github.com:lavanda-uk/site_minder.git | true) && pushd lvdam
   bundle config set --local local.site_minder ../site_minder
```

This approach will create a local repo.
You might need to update this repo main branch from time to time.
