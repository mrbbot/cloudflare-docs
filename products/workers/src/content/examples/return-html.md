---
order: 0
type: example
summary: Deliver an HTML page from an HTML string directly inside the Worker script.
demo: https://returning-html.workers-sites-examples.workers.dev
tags:
  - Originless
pcx-content-type: configuration
---

# Return small HTML page

<ContentColumn>
  <p>{props.frontmatter.summary}</p>
</ContentColumn>

```js
export default {
  fetch() {
    const html = `<!DOCTYPE html>
      <body>
        <h1>Hello World</h1>
        <p>This markup was generated by a Cloudflare Worker.</p>
      </body>
    `;
    return new Response(html, {
      headers: {
        "content-type": "text/html;charset=UTF-8",
      },
    });
  },
};
```

## Demo

<p><a href={props.frontmatter.demo}>Open demo</a></p>

<Demo src={props.frontmatter.demo} title={props.frontmatter.summary} height="150"/>
