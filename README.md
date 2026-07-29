# aftertrade-legal

Public pages for the **Aftertrade** iOS app, served by GitHub Pages.

| Page | URL | Used for |
| --- | --- | --- |
| Privacy Policy | `/privacy.html` | App Store Connect → App Privacy → Privacy Policy URL, and the in-app link under Profile → Privacy |
| Support | `/support.html` | App Store Connect → App Information → Support URL |
| Hub | `/` | Landing page linking both |

This repository is public because Apple requires both URLs to be reachable
without a login. It contains no application source.

## Editing

Plain HTML with one shared `style.css`; there is no build step. Push to `main`
and GitHub Pages redeploys within a minute or two. Colour values in `style.css`
mirror the app's `ColorsV2` tokens, and the pages follow the system light/dark
setting.

When changing the privacy policy, update the `Last updated` date at the top of
`privacy.html` in the same commit.

## Keeping the policy honest

The policy describes actual app behaviour, so it has to be revisited when any of
these change:

- which analytics events are sent, or what properties they carry
- adding, removing, or reconfiguring an SDK that sends data off the device
- any new network call, especially one carrying journal content
- the consent gate around usage analytics
- the set of permissions the app requests

It should also stay consistent with `Aftertrade/PrivacyInfo.xcprivacy` in the app
repository and with the App Privacy answers in App Store Connect. Apple compares
those, and a mismatch is a review rejection.
