
[liledix4 Says](../README.md) ❯ [How-To](index.md) ❯
# Get URLs from page

Use these code snippets in **Developer Tools**.

```js
{ // Get array
    const selector = '#your-css-selector';
    let arr = [];
    for (const a of document.querySelectorAll(selector)) {
        arr.push(a.href);
    }
    console.log(JSON.stringify(arr));
}
```

****

```js
{ // Get Markdown list
    const selector = '#your-css-selector';
    let arr = "";
    for (const a of document.querySelectorAll(selector)) {
        arr += `- ${a.href}\n`;
    }
    console.log(arr);
}
```

****

```js
{ // Get Markdown list with link texts
    const selector = '#your-css-selector';
    let arr = "";
    for (const a of document.querySelectorAll(selector)) {
        arr += `- ${a.innerText} | ${a.href}\n`;
    }
    console.log(arr);
}
```
