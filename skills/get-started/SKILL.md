---
name: get-started
description: Use when the user wants an AI headshot or styled portrait from their own photo, a photo edit such as background removal, to browse Photo AI Studio themes, or to check their Photo AI Studio credits and recent results.
---

# Get started with Photo AI Studio

Photo AI Studio creates new images from photos the user supplies: headshots, profile photos, and themed portraits, plus edits such as background removal. Browsing themes needs no account. Creating or editing an image needs a Photo AI Studio account, which connects the first time a tool needs it: Claude Code opens a sign-in page in the browser, and the user signs in there.

## Browse themes

Call `list_photo_themes` or `browse_themes` to show the available themes with their names and slugs. Let the user pick one.

## Create an image

1. Confirm the user has supplied a clear photo of the person for the image. Use only photos the user supplied, and only photos of people who agree to it.
2. Call `get_account` to read the credit balance. Each image spends credits from the user's account. If the balance is too low, tell the user and stop. Do not suggest a purchase link.
3. Tell the user which theme or edit you will use and that it spends credits, and wait for a yes.
4. Call `generate_photo` for a headshot or themed portrait, or `remove_background` to remove the background from a photo.
5. Results usually take one to three minutes. If the result is not ready, call `get_prediction` with the returned id until it is, then give the user the link to the finished image.

## Check the account

- `get_account` returns the account email, the credit balance, and the number of images generated.
- `list_predictions` lists recent images and edits, newest first, with their state and result links.

## Rules

- Never run a tool that spends credits without the user's yes, and never repeat a call the user did not ask for.
- Photos are sent to Photo AI Studio's AI model providers to create the images, and are handled as the privacy policy at https://www.photoaistudio.com/privacy-policy describes. Tell the user this before the first upload.
- Do not offer plans, prices, or credit purchases.
- Never ask the user for a password or a one-time code. The sign-in page handles authentication.
