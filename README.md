# Zep's Filters

This repository hosts filter lists for uBlock Origin/Adblock Plus/AdGuard and similar ad blockers that allow you to get rid of some annoyances from certain sites like Discord's Web UI and distractions like AI banners in sites.

## Installation

| Name | Subscribe button | Direct link |
| --- | --- | --- |
| **All** | [**(Subscribe)**](https://subscribe.adblockplus.org/?location=https://raw.githubusercontent.com/WhistlingZephyr/zeps-filters/main/filters/all.txt&title=Zep%27s%20Filters) | **`https://raw.githubusercontent.com/WhistlingZephyr/zeps-filters/main/filters/all.txt`** |
| Discord annoyances | [(Subscribe)](https://subscribe.adblockplus.org/?location=https://raw.githubusercontent.com/WhistlingZephyr/zeps-filters/main/filters/discord.txt&title=Zep's%20Filters%20-%20Discord) | `https://raw.githubusercontent.com/WhistlingZephyr/zeps-filters/main/filters/discord.txt` |
| AI-related distractions | [(Subscribe)](https://subscribe.adblockplus.org/?location=https://raw.githubusercontent.com/WhistlingZephyr/zeps-filters/main/filters/ai.txt&title=Zep's%20Filters%20-%20AI) | `https://raw.githubusercontent.com/WhistlingZephyr/zeps-filters/main/filters/ai.txt` |
| URL cleaner | [(Subscribe)](https://subscribe.adblockplus.org/?location=https://raw.githubusercontent.com/WhistlingZephyr/zeps-filters/main/filters/url-cleaner.txt&title=Zep's%20Filters%20-%20URL%20cleaner) | `https://raw.githubusercontent.com/WhistlingZephyr/zeps-filters/main/filters/url-cleaner.txt` |

## Tips

You can add additional filters that this filter list doesn't activate by default, e.g. for Discord:

- You can block sending typing events with `||discord.com/api/*/typing`.
-
    You can remove blocked messages entirely with:

    ```adblock
    discord.com##[class*="-groupStart"]:has([class*="-wrapper"] > [class*="-contents"] > [class*="-blockedSystemMessage"])
    ```

-
    You can remove the apps launcher & upload media icons from chat bar with:

    ```adblock
    discord.com##form > div > div[class*="-channelAppLauncher"]
    discord.com##form > div > div[class*="-channelBottomBarArea"] div[class*="-buttons"] > div[aria-label="Add Media"]
    ```

-
    You can remove quick access reactions with:

    ```adblock
    discord.com##div[aria-roledescription="Message"] > div[class*="-buttonContainer"] > [aria-label="Message Actions"] > div > :is(:has(~ [class*="-separator"]), [class*="-separator"])
    ```

-
    Or you can remove everything except the more button from message quick access with:

    ```adblock
    discord.com##div[aria-roledescription="Message"] > div[class*="-buttonContainer"] > [aria-label="Message Actions"] > div > :not([aria-label="More"])
    ```

-
    You can remove store, shop, & quest buttons from DM page with:

    ```adblock
    discord.com##[aria-label="Direct Messages"] li:has(a[href="/store"])
    discord.com##[aria-label="Direct Messages"] li:has(a[href="/shop"])
    discord.com##[aria-label="Direct Messages"] li:has(a[href="/quest-home"])
    ```

## Development

See [DEVELOPMENT.md](DEVELOPMENT.md).

## Related projects

- Web Annoyances Ultralist: <https://github.com/yourduskquibbles/webannoyances/>
- Discord Toggle Sidebar: <https://github.com/WhistlingZephyr/discord-toggle-sidebar/>
- Actually Legitimate URL Shortener Tool: <https://github.com/DandelionSprout/adfilt/blob/master/LegitimateURLShortener.txt>
