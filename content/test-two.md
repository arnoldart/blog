---
title: Your Title Goes Here
desc: The post description. Might be something that would interest the reader in less than 100 wooooords.
author: Reinaldy Rafli
github: aldy505
twitter: aldy505
telegram:
date: 2021-08-31
categories:
  - javascript
  - tutorial
---

# Heading 1

Dolor placeat commodi harum doloremque vel sequi, hic! Id quidem delectus
perspiciatis dolore numquam? Veritatis exercitationem ipsum facilis maiores
recusandae!

Elit a assumenda modi quo reprehenderit! Maiores vitae ipsam maxime fugiat
ratione Earum voluptas nam repudiandae rem quo Eum asperiores reprehenderit
fuga voluptatum quas pariatur eos, nobis! Atque quasi maxime quo tempora
repellendus Molestias aliquid totam consequuntur expedita officiis magni

## Heading 2

Dolor placeat commodi harum doloremque vel sequi, hic! Id quidem delectus
perspiciatis dolore numquam? Veritatis exercitationem ipsum facilis maiores
recusandae!

Elit a assumenda modi quo reprehenderit! Maiores vitae ipsam maxime fugiat
ratione Earum voluptas nam repudiandae rem quo Eum asperiores reprehenderit
fuga voluptatum quas pariatur eos, nobis! Atque quasi maxime quo tempora
repellendus Molestias aliquid totam consequuntur expedita officiis magni

### Heading 3

Dolor placeat commodi harum doloremque vel sequi, hic! Id quidem delectus
perspiciatis dolore numquam? Veritatis exercitationem ipsum facilis maiores
recusandae!

Elit a assumenda modi quo reprehenderit! Maiores vitae ipsam maxime fugiat
ratione Earum voluptas nam repudiandae rem quo Eum asperiores reprehenderit
fuga voluptatum quas pariatur eos, nobis! Atque quasi maxime quo tempora
repellendus Molestias aliquid totam consequuntur expedita officiis magni

# Foo Bar

- One
- Two
- Three

> no, not _that_ list

1. One
2. Two
3. Three

```javascript
import withShiki from '@stefanprobst/remark-shiki';
import fromMarkdown from 'remark-parse';
import toHAST from 'remark-rehype';
import toHTML from 'rehype-stringify';
import withHtmlInMarkdown from 'rehype-raw';
import shiki from 'shiki';
import { unified } from 'unified';

const createProcessor = async () => {
  const highlighter = await shiki.getHighlighter({ theme: 'github-dark ' });

  return (
    unified()
      .use(fromMarkdown)
      // @ts-ignore
      .use(withShiki, { highlighter })
      .use(toHAST, { allowDangerousHtml: true })
      .use(withHtmlInMarkdown)
      .use(toHTML)
  );
};

/**
 * Convert given markdown string to HTMl using remark
 * @param markdown - The markdown you want to convert
 * @return String containing HTML
 */
export const markdownToHtml = async (markdown: string): Promise<string> => {
  const processor = await createProcessor();
  const vfile = await processor.process(markdown);
  return vfile.toString();
};
```

Here's some Go code

```go
package main

import (
	"bytes"
	"errors"
	"strings"

	"github.com/lann/builder"
)

type UpsertBuilder builder.Builder

type upsertData struct {
	Dialect     int
	Into        string
	Columns     []string
	Values      [][]interface{}
	Key         []interface{}
	Replace     [][]interface{}
	Placeholder string
}

func init() {
	builder.Register(UpsertBuilder{}, upsertData{})
}

// dialect specifies database dialect used.
func (u UpsertBuilder) dialect(db int) UpsertBuilder {
	return builder.Set(u, "Dialect", db).(UpsertBuilder)
}

```
