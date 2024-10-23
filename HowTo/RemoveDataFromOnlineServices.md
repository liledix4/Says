
[liledix4 Says](../README.md) ❯ [How-To](index.md) ❯
# Remove data from online services

> ⚠️ **WARNING!**
> 
> Use the following pieces of code ONLY if you know what you're doing!
> 
> I'm not taking ANY responsibility if something gets broken. I won't be able to help you with the restoration of removed data: it won't be possible at all, it's irreversible. **Do everything at your own risk!**
> 
> If you prefer to be especially careful (which is a wise choice) – DM me for personal instructions! Besides, I'll be able to explain every line of code if you're concerned.

## Where to run the code?

First of all, you can't do it on mobile browsers (Android/iOS). You need PC.

<details>
    <summary>For snobs</summary>
    <blockquote>
        <p>Yes, I know, technically you <i>can</i> use mobile browsers or remote debugging, but in this case, most people will find the process overly complicated.</p>
        <p>If you feel like doing it on a mobile browser, no problem at all.</p>
    </blockquote>
</details>

You need to open **Developer Tools** – normally it's `F12`, alternatively `Ctrl+Shift+I`.

It doesn't matter which browser you use, Chromium-based or Firefox-based. The latest versions are most recommended.

## GitHub

### Unstar GitHub repositories

Modify this link and open it:

```url
https://github.com/<YOUR_USERNAME>?tab=stars
                   ↑-------------↑
```

You need to reload page every time after running the code.

```js
{
    const selector = 'button[data-ga-click*="click unstar button"]';
    for (const b of document.querySelectorAll(selector)) {
        b.click();
    }
}
```

### Unfollow GitHub users

Modify this link and open it:

```url
https://github.com/<YOUR_USERNAME>?tab=following
                   ↑-------------↑
```

You need to reload page every time after running the code.

```js
{
    const selector = 'input.btn.btn-sm[type="submit"][value="Unfollow"]';
    for (const b of document.querySelectorAll(selector)) {
        b.click();
    }
}
```

## X/Twitter

### Remove X/Twitter likes

Modify this link and open it:

```url
https://x.com/<YOUR_USERNAME>/likes
              ↑-------------↑
```

```js
{
    function run() {
        const selector = '[data-testid="unlike"]';
        const b = document.querySelectorAll(selector);
        if (b.length !== 0) {
            b[0].click();
        } else {
            window.scrollTo(0, document.body.scrollHeight);
        }
    }
    setInterval(run, 1000);
}
```

## YouTube

### Remove YouTube likes

Open this page: https://www.youtube.com/playlist?list=LL

```js
{
    const menuButton = `.ytd-item-section-renderer > #contents > .ytd-playlist-video-list-renderer:not([is-dismissed]) yt-icon-button`;
    const menuItemRemove = `tp-yt-iron-dropdown:not([style*='display: none;']) ytd-menu-service-item-renderer:last-child`;
    function run2() {
        document.querySelector(menuItemRemove).click();
    }
    function run() {
        const d = document.querySelectorAll(menuButton);
        if (d.length !== 0) {
            d[0].click();
            setTimeout(run2, 500);
        } else {
            window.scrollTo(0, document.body.scrollHeight);
        }
    }
    setInterval(run, 1000);
}
```
