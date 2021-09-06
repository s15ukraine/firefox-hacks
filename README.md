<h2>Firefox: hacks, tweaks, and productivity enhancements</h2>

Below are a few of our favorite Firefox hacks, tweaks, and productivity enhancements that can be made via [Configuration Editor](https://support.mozilla.org/en-US/kb/about-config-editor-firefox) (about:config page).

<h3>PRIVACY / SECURITY</h3>

Disable WebRTC

    media.peerconnection.enabled => false

Mozilla is actively working with Cloudflare and others on standardizing the [Encrypted Client Hello](https://blog.mozilla.org/security/2021/01/07/encrypted-client-hello-the-future-of-esni-in-firefox/) specification at the IETF. Firefox 85 replaces ESNI with ECH draft-08, and another update to draft-09 (which is targeted for wider interoperability testing and deployment) is forthcoming

    network.dns.echconfig.enabled => true
    network.dns.use_https_rr_as_altsvc => true

Enable DNS-over-HTTPS (DoH) in Firefox. [DoH](https://wiki.mozilla.org/Trusted_Recursive_Resolver) allows DNS to be resolved with enhanced privacy, secure transfers and comparable performance

    network.trr.mode => 2

Firefox already has an Enhanced Tracking Protection feature that blocks a list of known "fingerprinters" when your privacy settings are set to Standard (the default) or Strict, whereas [Fingerprinting Protection](https://support.mozilla.org/en-US/kb/firefox-protection-against-fingerprinting) is a different, experimental feature under heavy development in Firefox

    privacy.resistFingerprinting => true
    privacy.trackingprotection.fingerprinting.enabled => true

Enable IDN Punycode

    network.IDN_show_punycode => true

Disable Geolocation Tracking

    geo.enabled => false

Disable WebGL

    webgl.disabled => true

Disable HTTP referer

    network.http.sendRefererHeader => 0

Disable Microphone And Camera Status

    media.navigator.enabled => false

Disable notifications (copy, paste, or cut something)

    dom.event.clipboardevents.enabled => false

Disable Battery Charge Level

    dom.battery.enabled => false

Web pages won't be allowed to manipulate or block the context menu

    dom.event.contextmenu.enabled => false

Disables the Widevine Content Decryption Module provided by Google

    media.gmp-widevinecdm.enabled => false

Disable Pocket integration

    extensions.pocket.enabled => false

<h3>UI</h3>

Prevent Firefox from exiting when you close the last tab

    browser.tabs.closeWindowWithLastTab => false

This preference controls whether lines in View Source that are too long to fit the window will wrap to the next line or cause a horizontal scroll bar

    view_source.wrap_long_lines => true

UI density: adjust Firefox user interface density to something more appropriate on desktop

    browser.uidensity

    0 -> normal (Default)
    1 -> compact
    2 -> touch

<h3>COLOR CORRECTION</h3>

Color management allows images and colors to be displayed consistently across a variety of devices; Firefox recognizes embedded ICC profiles in image files and uses a local color profile to perform the color adjustments; this preference determines if Firefox should make these adjustments

    gfx.color_management.mode

    0 -> Color management disabled (Default in Firefox 3.)
    1 -> Full color management
    2 -> Color management applied only to tagged images (Default in Firefox 3.5.)
