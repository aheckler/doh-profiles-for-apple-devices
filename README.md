# DNS over HTTPS iOS Profiles

One of the new features in iOS 14 is [the ability to encrypt DNS](https://developer.apple.com/videos/play/wwdc2020/10047/) without needing a VPN app. The profiles in this repo use this new ability to enable DNS over HTTPS for the entire system. This increases your security and privacy.

## Compare

All profiles use DNS over HTTPS and support both IPv4 and IPv6.

| Profile                                    | Filters Malware | Filters Adult Content |                                 Privacy Policy                                |
|--------------------------------------------|:---------------:|:---------------------:|:-----------------------------------------------------------------------------:|
| cloudflare-doh                             |        No       |           No          | [Link](https://developers.cloudflare.com/1.1.1.1/privacy/public-dns-resolver) |
| cloudflare-doh-filter-malware              |       Yes       |           No          | [Link](https://developers.cloudflare.com/1.1.1.1/privacy/public-dns-resolver) |
| cloudflare-doh-filter-malware-adultcontent |       Yes       |          Yes          | [Link](https://developers.cloudflare.com/1.1.1.1/privacy/public-dns-resolver) |
| google-doh                                 |        No       |           No          |         [Link](https://developers.google.com/speed/public-dns/privacy)        |
| quad9-doh                                  |       Yes       |           No          |                  [Link](https://www.quad9.net/home/privacy/)                  |

## Install

1. Using Safari, choose the desired profile above.
2. Tap the **Raw** button.
3. You'll be asked if you want to allow the profile download. Tap **Allow**.
4. You'll see a *Profile Downloaded* alert. Tap **Close**.
5. Open the *Settings* app. There will be a *Profile Downloaded* section near the top. Open that.
6. Inside, it will show the profile name and info. Tap **Install**.
7. Enter your passcode.
8. You'll see a warning that the profile might monitor your network traffic, and that it's unsigned. Tap **Install**.
9. The profile will be installed. Tap **Done**.

If you're scared of the warning in Step 8, I'd suggest just using a VPN app instead, such as [Cloudflare's 1.1.1.1 app](https://1.1.1.1/) or one [suggested by Wirecutter](https://www.nytimes.com/wirecutter/reviews/best-vpn-service/).

## Uninstall

1. Open *Settings* > *General* > *Profile*.
2. Tap the profile.
3. Tap **Remove Profile**.
4. Enter your passcode.
5. Tap **Remove**.
