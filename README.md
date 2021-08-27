# Welcome to the Lavanda Engineering team

Welcome to the "dream team"! We're so happy to have you!

Below you'll find some information about your new team. Feel free to add to this repo by raising a PR.


## The way we work

We, engineers at Lavanda, are part of the broader Product function. We're a relaxed bunch and like to have fun working together and learning from each other. We employ a Product first design-led process and strive to be Product minded engineers. Read more about "The Product-Minded Software Engineer" here: https://blog.pragmaticengineer.com/the-product-minded-engineer/.

## Engineering team ethos

We care most about:
 - well crafted and tested software
 - delivering a great product that delights our customers
 - supporting each other along the way through intense collaboration
 - having fun whilst doing it
 - being kind and honest
 - high level of professionalism

### High level of professionalism

Whilst all the things "we care most about" are mostly self-explanatory, perhaps the point about "high level of professionalism" warrants explanation.

In our context, high level of professionalism means:

1. Short feedback loop - regular and visible code commits

 - Work in small batches and deliver value incrementally
 - Commit early and often
 - When not pairing, submitting code for review often

In practice, on a regular work day it is expected that you:
 - produce or co-produce (pairing/mobbing) several code commits
 - when not fully paired on, make your code visible through code reviews
    - strive for small final pull requests - exceptionally, if/when the PR grows larger than around 500 lines changes because there is no pragmatic way to break it down, use draft PRs to get early feedback
    - N.B.: If you spend more than a day without submitting code for review that is a strong sign that you are probably learning the system/domain and would benefit considerably from spending 100% of your time pairing with a team member who's been at Lavanda for longer. Speak to your squad lead or line manager as soon as you realise this is the case.

2. Superb communication 

 - Clear and concise written communication in offline setting
 - When working from a TimeZone (TZ) or working hours that don't overlap entirely with your direct colleagues, ensure work handover is smooth in writing including all the context of decisions and tradeoffs considered to enable progress while working alone 
 - When in doubt, favour over-communication (TODO: specific tips required)

#### What you can expect from the team

A supportive and trusting environment and (hopefully) lots of fun.

## Methodology

Below is a message that tries to summarise the way we strive to work - extracted from an email sent to a candidate in mid-2021 in response to a question regarding how we like to work:

```
XP (extreme programming) is a term that can be scary for people new to it, perhaps due to the "extreme" word. It is relatively old (was created in 1996) and it's interesting to see that most teams that try it tend to adopt it and enjoy it. 
I'll start by saying that as a team we embody the five core values of XP: communication, simplicity, feedback, courage, and respect.
In terms of XP practices/rules, we are not fundamentalists. The team works together to iterate/refine the subset of rules we adopt from XP and make it work better for each and every one member of the team, following one of core rules of XP which is " Fix XP when it breaks" which equates to starting with XP Rules and then adapting, changing without hesitation what doesn't work well.
For example, we tried at some point in time (a couple of years ago) to pair nearly 100% of the time (like XP originally describes) but that revealed to be unsuitable for the team. Today we do it an average of about 50% of the time.
Overall we currently adopt a subset of the originally "prescribed" by XP, from which I would highlight:
 - simple design
 - user stories
 - small releases
 - stand-up meeting
 - rotation (moving people around)
 - code written to agreed standards
 - acceptance tests are run often
 - use spikes where applicable
 - collective ownership
 - integrate often
 - (partially) TDD - on backend projects, we think we do this quite well. On the frontend, we have room for improvement
 - (partially) pair programming (particularly useful for onboarding, specially in remote setting)
```

## Agile process in 1 sentence

Requirement formulation in Product board -> UX Design -> Card(s) moved to trello -> Scope clarification/on-demand planning -> Move to "Next up" -> Engineer pair/group start building and move card to "In progress" -> Peer code review (if code not paired on fully) -> QA -> Production

## Agile cerimonies

Currently we do:
 - Squad standups (starting at 9AM UK time every day from Tuesday to Friday)
 - Product checkpoint (every Monday at 9AM UK time)
 - Team retrospetive (every other week, on Fridays at 10:30AM UK time)

## Git approach

We follow a `Feature Branch Workflow` approach. All our developments are made in feature branches and we utilise `main` as a single special branch that holds all production ready code.

As a result:

- code only gets merged into `main` through a pull request (PR)
- a PR should only be merged into `main` when it's production ready
- a PR needs to be up to date with `main` in order to be merged - to do so we `rebase` (`git rebase main`)
- if the feature requires stakeholder involvement/user testing, the branch should be made available in a dedicated testing environment (staging, branch deploy or heroku review app)

Here is an illustration of the process:

![Git-feature branch workflow](https://user-images.githubusercontent.com/22520561/141101792-a9ea474f-69e5-40c5-ad79-40f99c56e733.png)

More info: https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow

### Branch naming convention

Format: <type_of_change>/<change_title>

`type_of_change` possible values: api,feature,refactor,fix,bundle,package,deps(for dependencies),setup,perf(for performance)

Examples:
 - feature/add-new-bookings-view
 - api/add-workspace-invoice-list-endpoint
 - fix/block-calendar-when-default-setting-is-updated
 - package/add-snyk
 - perf/tune-multi-calendar-queries
 - refactor/improve-airbnb-booking-import

### Branch etiquette

Make sure to coordinate with the authors of a branch before considering making any change to said branch, whatever the change might be (e.g.: adding a commit, rebasing).

### Commit hygiene

Good commits can be very helpful, but it takes practise to write good commits.

#### What makes a good commit?

YMMV. Last time we discussed, we agreed as a team that a good commit should have the following characteristics:

- atomic, focuses on a single point of change;
- includes a commit message that is concise and clear, providing a good understanding of what is included.

#### Commit conventions

Example: `[feature] Add ability to destroy payments`

- Use a prefix between square brackets to denote the kind of commit:
  - feature: A new feature
  - fix: A bug fix
  - docs: Documentation only changes
  - style: Changes to visual styling
  - lint: Formatting, missing semi-colons, white-space, etc
  - refactor: A code change that neither fixes a bug nor adds a feature
  - perf: A code change that improves performance
  - test/spec: Adding or making changes to tests
  - config: Changes to project configuration
  - setup: Project setup
  - deps: Introduction or removal of dependencies such as external libs, ruby gems and npm modules
  - logs: Introduction of logs to improve troubleshooting
- Limit the subject line to 50 characters;
- Capitalize the subject line;
- Do not end the subject line with a period;
- Use the [imperative mood](https://en.wikipedia.org/wiki/Imperative_mood) in the subject line.

Originally inspired by: https://chris.beams.io/posts/git-commit/

## Platform overview

For a platform overview, please refer to private repo https://github.com/lavanda-uk/welcome-private#platform-overview

## Staging

Usually, `staging` environment is running the `main` branch code, i.e. whatever is in production. 
However, there are cases in which you might want to run a different branch on staging machine. 
For example, you might want to demonstrate a feature branch to the other members of the company
(see Quality Street session). In that case, you need to _get hold of_ staging and deploy your feature branch.

Getting hold of staging is the following process:

1. You go to the slack channel with name `#eng-a-backend`. 
2. You check the topic/description of the channel at the top. If it says "Current branch on staging: `main` with staging data",
then you can get hold of staging.
3. If you can get hold of it, you change the topic of the channel to refer to the branch you want to deploy. Example:
"Current branch on staging: `feature/confetti-on-property-publication` with staging data".
4. If you cannot get hold of staging, you have to look into the channel message history to find out who is holding staging and ask them
whether you can take it from them.
5. When you have changed the topic of the channel to have your branch name in, then you deploy your branch to staging. This can be done
either from the Heroku dashboard, or using the `heroku` command line interface.
6. As soon as you don't need staging any more, it is a good idea to deploy `main` branch and change the topic of the slack channel
accordingly.

## Tooling/account setup

- [ ] Google suite
- [ ] Slack
- [ ] LastPass
- [ ] Heroku
- [ ] Netlify
- [ ] Trello
- [ ] ProductBoard
- [ ] Tuple
- [ ] Sentry
- [ ] Auth0
- [ ] FullStory

### Install suggestions for MacOS users 
 - Heroku CLI: `brew tap heroku/brew && brew install heroku`
 - Postgres `brew install postgres` (alternative: asdf)
 - Redis `brew install redis`
 - Misc: `brew install asdf tar gpg openssl wget cmake pkg-config libpq`

### Other
  * [Sharing credentials or sensitive files securely](#sharing-credentials-or-sensitive-files-securely)
  * [Private Gems](./private_gems.md)
  * [Error conventions](./error-format.md)
  * [VSCode setup tips](./VSCode-setup.md)
     
## Sharing credentials or sensitive files securely

To share credentials within Lavanda, please always use your company LastPass account.
To share credentials with external entities, please always use http://1ty.me/.
To securely share files, encrypt them using GPG before sending via email/slack/whatever other insecure channel.

Instructions: [GPG howto guide](gpg-howto.md)
Team keys: [GPG keys](gpg-keys.md)

