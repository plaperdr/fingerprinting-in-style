
# Artifact for "Fingerprinting in Style: Detecting Browser Extensions via Injected Style Sheets"
Paper by Pierre Laperdrix, Oleksii Starov, Quan Chen, Alexandros Kapravelos and Nick Nikiforakis to appear at USENIX Security '21

Link to the paper will be added soon

### Extension
The **extension** folder contains our defense prototype that protects users against CSS-based extension fingerprinting.
It redirects _getComputedStyle_ calls made on 222,642 specific elements into a special Shadow DOM copy that will return benign measurements. 

### Demo page
Link

In order to demonstrate the effectiveness of our extension, we have a demo page that detects 11 browser extensions through the style they inject on any page.
The 11 triggers we use were working as of January 4th 2021 but the targeted extensions may have been updated since then and so the detection may be altered. 

List of tested extensions (last tested versions in parentheses):
* [Data Scraper - Easy Web Scraping](https://chrome.google.com/webstore/detail/data-scraper-easy-web-scr/nndknepjnldbdbepjfgmncbggmopgden)
(v.3.299.84)
* [TTSReaderX In-Page Text to Speech](https://chrome.google.com/webstore/detail/ttsreaderx-in-page-text-t/pakknklefcjdhejnffafpeelofiekebg)
(v.1.32.5)
* [Touch VPN](https://chrome.google.com/webstore/detail/touch-vpn-secure-and-unli/bihmplhobchoageeokmgbdihknkjbknd)
(v.4.1.0)
* [AdBlocker by Trustnav](https://chrome.google.com/webstore/detail/adblocker-by-trustnav/dgbldpiollgaehnlegmfhioconikkjjh)
(v.2.8.1)
* [MozBar](https://chrome.google.com/webstore/detail/mozbar/eakacpaijcpapndcfffdgphdiccmpknp)
(v.3.1.252)
* [Disconnect](https://chrome.google.com/webstore/detail/disconnect/jeoacafpbcihiomhlakheieifhpjdfeo)
(v.20.3.1.1)
* [TripAdvisor Browser Button](https://chrome.google.com/webstore/detail/tripadvisor-browser-butto/oiekdmlabennjdpgimlcpmphdjphlcha)
(v.1.1.2.4)
* [Awesome Screenshot: Screen Video Recorder](https://chrome.google.com/webstore/detail/awesome-screenshot-screen/nlipoenfbbikpbjkfpfillcgkoblgpmj)
(v.4.3.12)
* [Hunter: Find email addresses in seconds](https://chrome.google.com/webstore/detail/hunter-find-email-address/hgmhmanijnjhaffoampdlllchpolkdnj)
(v.1.18.5)
* [Screenshot reader](https://chrome.google.com/webstore/detail/screenshot-reader/enfolipbjmnmleonhhebhalojdpcpdoo)
(v.1.0.8.2)
* [Cently (Coupons at Checkout)](https://chrome.google.com/webstore/detail/cently-coupons-at-checkou/kegphgaihkjoophpabchkmpaknehfamb)
(v.5.9.0)

#### Instructions to test the extension
1. Download the extension by pulling the repo or downloading the corresponding zip file [HERE]().
2. On a Chromium-based browser like Chrome, visit the address "chrome://extensions/".
3. Activate "Developer mode" on the right and click on "Load unpacked extension".
![Extension page on Chrome](images/extension-ui.png)
4. Select the folder which contains the extension (the one from the repo or the unzipped file).
![Extension enabled on Chrome](images/extension-activated.png)
5. Visit the [demo page]() and all fingerprinted extensions should be marked as "non" detected when the defense is active. 
Links to install fingerprinted extensions can be found on the demo page.