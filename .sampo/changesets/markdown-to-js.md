---
cargo/satteri-mdxjs: patch
cargo/satteri-napi: minor
npm/satteri: minor
---

Added `markdownToJs`, the plain-Markdown counterpart to `mdxToJs`. It compiles Markdown to a JavaScript module without MDX semantics: `{...}` expressions, JSX tags, and `import`/`export` lines are treated as ordinary Markdown text. It accepts the same options as `mdxToJs`; for sources containing raw HTML, enable `features: { rawHtml: true }`.

```ts
import { markdownToJs } from "satteri";

const { code } = markdownToJs("Hello {world}");
// `{world}` stays literal text instead of becoming a JS expression
```
