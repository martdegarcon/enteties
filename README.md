# Account Flow

A pack of **seven microinteractions** across the life of an account: sign up, verify, recover, set up a profile and manage devices.

Each one takes a familiar UI pattern and shows its state through type and motion, instead of adding more UI.

**Live demo:** `https://<your-username>.github.io/account-flow/`

| # | Step | Microinteraction | Status |
|---|------|------------------|--------|
| 01 | Sign up | **[Password Weight](01-password-weight/)**: password strength is the font weight | ✅ Live |
| 02 | Verify email | **OTP**: digits roll like drums; a right code fuses into a single plate | Soon |
| 03 | Code didn’t arrive | **Resend**: the label writes itself in letter by letter instead of a timer | Soon |
| 04 | Recovery key | **[Copy Key](04-copy-key/)**: the copied text flies into the button icon | ✅ Live |
| 05 | Profile photo | **Upload**: the file name is the progress bar | Soon |
| 06 | About you | **Limit**: text tightens its tracking near the character limit | Soon |
| 07 | Signed-in devices | **Strike**: swipe draws a strike-through and the row folds away | Soon |

## Structure

```
account-flow/
├── index.html            gallery with live previews
├── shared/
│   ├── tokens.css        colors, motion curve, base layout, pack navigation
│   └── haptics.js        Android vibration + iPhone tap haptics
├── 01-password-weight/
├── 04-copy-key/
└── …
```

Every microinteraction loads `shared/tokens.css` and `shared/haptics.js`, so the whole pack shares one look and one motion language:

```css
--ease: cubic-bezier(.25,1,.5,1);  /* one curve for everything */
--move: .5s;                       /* position / size */
--fade: .35s;                      /* opacity / blur */
```

## Haptics

- **Android (Chrome, Firefox):** uses the Vibration API with patterns, for any event.
- **iPhone (iOS 26.5+):** Safari has no Vibration API. The system haptic tick only plays when a finger directly taps a real native `<input type="checkbox" switch>`, so an invisible one sits over tappable controls. Typing and timed events don’t vibrate on iPhone.
- **Desktop:** nothing.

## Stack

- HTML, CSS and vanilla JS, with no build step and no dependencies
- [Onest](https://fonts.google.com/specimen/Onest) variable font

## Run locally

```bash
npx serve .
```

## Deploy

Go to **Settings → Pages → Deploy from a branch**, then pick `main` and `/ (root)`.

## Credits

Design and code by Marat Murzagaliev. MIT License.
# enteties
