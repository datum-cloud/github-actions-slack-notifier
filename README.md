# github-actions-slack-notifier

a shareable actions workflow to post build status updates to Slack. 

You can get started by creating a sample workflow like below:

```yaml
name: Notify slack

on: [push]

jobs:
    notify-slack:
        runs-on: ubuntu-latest
        steps:
          - name: Send message to Slack channel
            uses: datumforge/github-actions-slack-notifier@v1.0.2
            with:
              type: start
             # type: custom <- when using type "custom" you can feed in your own templates / message using the "message" parameter
             # message: "Matt is the best"
              channel_id: C05QJ8EKP0V # you can get this by clicking on the channel in Slack and under the "about" tab the CHannel ID is listed at the bottom
              slack_bot_token: ${{ secrets.SLACK_BOT_TOKEN }}
              mentions: "@manderson" # you need to put the @ and either group of users in slack or a user handle directly
```

# Default message types

The default message types:

- default
- start
- end
- failed
- custom

# Inputs

| Name          | Description                                             |
| ------------- |---------------------------------------------------------|
| `CHANNEL_ID` | The slack channel id                                     |
| `MESSAGE`       | The message display in first block of notification    |
| `SLACK_BOT_TOKEN`       | OAuth token of your slack app                 |