# probot-radar

> a GitHub Integration built with [probot](https://github.com/probot/probot) that creates status update issues (radars).

A bot that collates issues with labels and presents them in as a tracking issue in another repo (i.e `what's on my radar` like feature)
![probot-radar](screenshot.png)
## Configuration
Adding a `.github/radar.yml` will override these defaults

```
#Number of days before closing a radar issue (not implemented yet!)
days: 7

#Issues with labels to collate
labels: ['blocked','ready-for-review', 'tracking']

#A separate repo to create the radar issues along with radar specfic labels
radar:
    repo: 'radar-repo'
    labels: ['radar']
```
## Setup
```
# Install dependencies
npm install

# Run the bot
npm run
```

For more information, see the [documentation for probot](https://github.com/probot/probot).

## Deploying to Heroku

0. [![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy) - Click this button and pick an **App Name** that Heroku is happy with. Before you can complete this, you'll need config variables from the next step.

0. In another tab, [create an integration](https://github.com/settings/integrations/new) on GitHub, using `https://[yourappname].herokuapp.com/` (replacing `[yourappname]` with the name from step 1) as the **Homepage URL**, **Callback URL**, and **Webhook URL**. The permissions and events that your bot needs access to will depend on what you use it for. Read more about [creating an integration](https://developer.github.com/early-access/integrations/creating-an-integration/).

0. After creating your GitHub integration, go back to the Heroku tab and fill in the configuration variables with the values for the GitHub Integration
