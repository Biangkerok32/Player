# Just (Video) Player 

[![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/moneytoo/Player)](https://github.com/moneytoo/Player/releases/latest)
[![Google Play](https://img.shields.io/endpoint?color=green&logoColor=green&url=https%3A%2F%2Fplayshields.herokuapp.com%2Fplay%3Fi%3Dcom.brouken.player%26l%3DGoogle%2520Play%26m%3Dv%24version)](https://play.google.com/store/apps/details?id=com.brouken.player)
[![F-Droid](https://img.shields.io/f-droid/v/com.brouken.player)](https://f-droid.org/packages/com.brouken.player/)
![Lines of code](https://img.shields.io/tokei/lines/github/moneytoo/Player)
[![ExoPlayer](https://img.shields.io/badge/ExoPlayer-v2.12.2-007ec6)](https://github.com/google/ExoPlayer)

Android video player based on [ExoPlayer](https://github.com/google/ExoPlayer)

It uses ExoPlayer's ``extension-ffmpeg`` with [all its audio formats](https://exoplayer.dev/supported-formats.html#ffmpeg-extension) enabled (it can handle even special formats like AC3, EAC3, DTS, DTS HD, TrueHD etc.).

It properly synces audio with video track when using Bluetooth earphones/speaker. (I was not able to find any other nice ExoPlayer based video player so I created this one.)

## Supported formats

 * **Audio**: Vorbis, Opus, FLAC, ALAC, PCM/WAVE (μ-law, A-law), MP1, MP2, MP3, AMR (NB, WB), AAC (LC, ELD, HE; xHE on Android 9+), AC-3, E-AC-3, DTS, DTS-HD, TrueHD
 * **Video**: H.263, H.264 AVC (Baseline Profile; Main Profile on Android 6+), H.265 HEVC, MPEG-4 SP, VP8, VP9, AV1
 * **Containers**: MP4, MOV, WebM, MKV, Ogg, MPEG-TS, MPEG-PS, FLV
 * **Subtitles**: SRT, SSA, ASS, TTML, VTT

HDR and HDR10+ video playback on compatible/supported hardware.

## Screenshot

<img src="https://raw.githubusercontent.com/moneytoo/Player/master/fastlane/metadata/android/en-US/images/phoneScreenshots/1.png" width="540">

## Features

 * Audio/subtitle track selection
 * Playback speed control
 * Horizontal swipe to quickly seek
 * Vertical swipe to change brightness (left) / volume (right)
 * PiP (Picture in Picture) on Android 8 or higher
 * Resize (fit/crop)
 * No ads, tracking or even the Internet permission

To load an external (non-embedded) subtitles, long press the file open action in the bottom bar.

**`WRITE_SETTINGS` ("Modify system settings") permission**: When the system file chooser is opened, it will always use current system orientation, even if the Player app sets its own. Granting this permission via adb (`adb shell pm grant com.brouken.player android.permission.WRITE_SETTINGS`) or App info screen will allow this app to temporarily enable Auto-rotate to at least partially mitigate [this imperfection](https://issuetracker.google.com/issues/141968218).

Donate: [PayPal](https://paypal.me/MarcelDopita) | [Bitcoin](https://live.blockcypher.com/btc/address/bc1q9u2ezgsnug995fv0m4vaxa90ujjwlucp78w4n0) | [Litecoin](https://live.blockcypher.com/ltc/address/LLZ3fULGwxbs6W9Vf7gtu1EjZvviCka7zP)

## Download

[<img src="https://play.google.com/intl/en_us/badges/static/images/badges/en_badge_web_generic.png" alt="Get it on Google Play" height="75">](https://play.google.com/store/apps/details?id=com.brouken.player)
[<img src="https://fdroid.gitlab.io/artwork/badge/get-it-on.png" alt="Get it on F-Droid" height="75">](https://f-droid.org/packages/com.brouken.player/)
[<img src="https://raw.githubusercontent.com/andOTP/andOTP/master/assets/badges/get-it-on-github.png" alt="Get it on GitHub" height="75">](https://github.com/moneytoo/Player/releases/latest)

Other communication channels to get in touch: application thread on [XDA Developers](https://forum.xda-developers.com/t/app-5-0-just-video-player-no-bluetooth-lag-exoplayer-ffmpeg-audio-codecs.4189183/), subreddit on [reddit](https://www.reddit.com/r/JustPlayer/), entry on [AlternativeTo](https://alternativeto.net/software/just-video-player/)

## Other open source Android video players

Here's a comparison table presenting all available and significant open source video players for Android I was able to find. Just Player is something like 80% feature complete. It will probably never have dozens of options or some rich media library UI. It will never truly compete with feature rich VLC. It just attempts to provide functional feature set and motive others to create greater players based on amazing ExoPlayer.

| App name (source)                                                           | Tested version        | Media engine                                       | Internet access | Subtitles (embedded)                                  | DTS/AC3/E-AC3 decoders | PiP                      | Cutout (notch) | HDR (4K 60 FPS HEVC)        | HDR (4K 60 FPS VP9)         | Gestures                  |
| --------------------------------------------------------------------------- | --------------------- | -------------------------------------------------- | --------------- | ----------------------------------------------------- | ---------------------- | ------------------------ | -------------- | --------------------------- | --------------------------- | ------------------------- |
| [Fermata Media Player](https://github.com/AndreyPavlenko/Fermata)           | 1.7.3                 | MediaPlayer, ExoPlayer and libVLC                  | Yes             | 🟢 Yes (libVLC only)                                  | 🟢 Yes (libVLC only)   | 🔴 No                    | 🔴 No          | 🟢 Yes                      | 🔴 No                       | 🟡 Seek/Volume            |
| [Just (Video) Player](https://github.com/moneytoo/Player)                   | 0.11                  | [ExoPlayer](https://exoplayer.dev/)                | No              | 🟢 Yes                                                | 🟢 Yes                 | 🟢 Yes                   | 🟢 Yes         | 🟢 Yes                      | 🟢 Yes                      | 🟢 Seek/Volume/Brightness |
| [Kodi](https://github.com/xbmc/xbmc)                                        | 18.9                  | ?                                                  | Yes             | 🟢 Yes                                                | 🟢 Yes                 | 🔴 No                    | 🔴 No          | 🟢 Yes                      | 🔴 No                       | 🔴 No                     |
| [mpv](https://github.com/mpv-android/mpv-android)                           | 2020-11-16-release    | [libmpv](https://github.com/mpv-player/mpv)        | Yes             | 🟢 Yes                                                | 🟢 Yes                 | 🔴 No                    | 🟢 Yes         | 🟡 Yes (performance issues) | 🟡 Yes (performance issues) | 🟢 Seek/Volume/Brightness |
| [Nova Video Player](https://github.com/nova-video-player/aos-AVP)           | 4.49.15-20201210.0809 | ?                                                  | Yes             | 🟢 Yes                                                | 🟢 Yes                 | 🟢 Yes                   | 🔴 No          | 🟢 Yes                      | 🔴 No                       | 🔴 No                     |
| [VLC](https://code.videolan.org/videolan/vlc-android)                       | 3.3.2                 | [libVLC](https://www.videolan.org/vlc/libvlc.html) | Yes             | 🟡 Yes (may be cut off in some video display formats) | 🟢 Yes                 | 🟢 Yes                   | 🟢 Yes         | 🟢 Yes                      | 🔴 No                       | 🟢 Seek/Volume/Brightness |
| [YetAnotherVideoPlayer](https://github.com/shadow578/YetAnotherVideoPlayer) | 1108                  | [ExoPlayer](https://exoplayer.dev/)                | Yes             | 🔴 No                                                 | 🔴 No                  | 🟡 Yes (with black bars) | 🔴 No          | 🔴 No                       | 🔴 No                       | 🟡 Volume/Brightness      |

_The tested HDR VP9 video was "The World in HDR" from [Kodi Sample](https://kodi.wiki/view/Samples#4K_.28UltraHD.29), running on OnePlus 7 (Snapdragon 855)._

To find other video players (including non-FOSS), check out [a list on IzzyOnDroid](https://android.izzysoft.de/applists/category/named/multimedia_video_player).
