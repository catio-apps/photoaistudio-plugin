# Photo AI Studio plugin for Claude Code

This plugin lets Claude Code create images from photos you supply, using your own Photo AI Studio account: headshots, profile photos, and themed portraits, plus edits such as background removal.

## Install

Run these commands in Claude Code:

```
/plugin marketplace add catio-apps/photoaistudio-plugin
/plugin install photo-ai-studio@photoaistudio-plugin
```

From a shell, the equivalent is `claude plugin marketplace add catio-apps/photoaistudio-plugin` followed by `claude plugin install photo-ai-studio@photoaistudio-plugin`.

## Sign in

The plugin connects to the remote MCP server at `https://www.photoaistudio.com/api/mcp` and uses OAuth. The first time a tool needs your account, run `/mcp`, select the `photo-ai-studio` server, and complete the sign-in in your browser. Sign in to your Photo AI Studio account and approve access. You never type a password or a code into Claude Code.

Using an API key is optional. If you prefer one, create it in your account and add the server yourself with a bearer header, for example `claude mcp add --transport http photo-ai-studio https://www.photoaistudio.com/api/mcp --header "Authorization: Bearer YOUR_API_KEY"`. Do not commit a key to a repository.

## What the plugin contains

- `.mcp.json`: the remote MCP server definition.
- `skills/get-started/SKILL.md`: a skill that tells Claude when and how to use the tools.

The plugin runs no local code and no hooks. It sends requests only to `https://www.photoaistudio.com/api/mcp`, on behalf of the account you sign in with.

## What you can ask for

- Browse the available photo themes. This needs no account.
- Create a headshot or themed portrait from a photo you supply.
- Remove the background from a photo.
- Check your credit balance and list your recent results.

Creating or editing an image spends credits that your account already holds. Claude asks for your approval first. Results usually take one to three minutes.

## Your photos

The plugin works from photos you supply. Photos are sent to Photo AI Studio's AI model providers to create the images, and are handled as the privacy policy describes. Use only photos of people who agree to it.

## Privacy, terms, and support

- Privacy policy: https://www.photoaistudio.com/privacy-policy
- Terms of service: https://www.photoaistudio.com/terms-conditions
- Support: https://www.photoaistudio.com/contact
- Website: https://www.photoaistudio.com

## License

MIT. See [LICENSE](./LICENSE). Copyright 2026 EDSDEV INC.
