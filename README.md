# Cloudflare DNS over HTTPS iOS Profile

One new feature in iOS 14 is [the ability to encrypt DNS](https://developer.apple.com/videos/play/wwdc2020/10047/) without needing a VPN app. This profile uses this new ability to enable DNS over HTTPS for the entire system. Specifically, it sends encrypted DNS queries to [Cloudflare's public DNS service](https://1.1.1.1/dns/). 

This profile uses the following resolvers:

```
1.1.1.2
1.0.0.2
2606:4700:4700::1112
2606:4700:4700::1002
```

These are slighty different from the `1.1.1.1` set of resolvers in that [they block malware](https://developers.cloudflare.com/1.1.1.1/1.1.1.1-for-families), whereas `1.1.1.1` does not.

## Installation

1. Download the `cloudflare-dns-over-https.mobileconfig` file to your computer.
2. Via AirDrop, Dropbox, or some other method, transfer the file to your iOS device and open it.
3. You'll see a *Profile Downloaded* alert. Tap **Close**.
4. Open the *Settings* app. There will be a *Profile Downloaded* section near the top. Open that.
5. Inside, it will show the "Cloudflare DNS over HTTPS" profile. Tap **Install**.
6. Enter your passcode.
7. You'll see a warning that the profile might monitor your network traffic, and that it's unsigned. Tap **Install**.
8. The profile will be installed. Tap **Done**.

If the warning in Step 7 scares you, I'd suggest [using Cloudflare's app](https://apps.apple.com/us/app/1-1-1-1-faster-internet/id1423538627) instead. However, it has one particular disadvantage that inspired me to create this profile in the first place. Specifically, if you whitelist a network where you don't need the VPN to be active (e.g. your home WiFi), the encrypted DNS functionality *will also be disabled!* 

This profile gives you always-on encrypted DNS **and** the ability disable the 1.1.1.1 app on certain networks.

## Verify

Once the profile has been installed, you can verify it's working like so:

1. Disable any VPN apps you have installed.
2. In any browser, open this URL: https://1.1.1.1/help
3. Below *Debug Information*, the top two lines should say:
  ```
  Connected to 1.1.1.1            Yes
  Using DNS over HTTPS (DoH)      Yes
  ```
4. Under *Connectivity to Resolver IP Addresses*, every line should say `Yes`.

## Uninstall

1. Open *Settings* > *General* > *Profile*.
2. Tap the "Cloudflare DNS over HTTPS" profile.
3. Tap **Remove Profile**.
4. Enter your passcode.
5. Tap **Remove**.
