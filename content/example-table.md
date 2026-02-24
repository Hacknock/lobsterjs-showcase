# Tables

lobster.js supports standard Markdown tables plus two powerful extensions: **cell merging** and **silent tables** for layout grids.

## Standard table

```markdown
| Name       | Type    | Description                  |
| :--------- | :------ | :--------------------------- |
| `src`      | string  | Path or URL to Markdown file |
| `container`| Element | Target DOM element           |
| returns    | Promise | Resolves when rendered       |
```

**Result:**

| Name        | Type    | Description                  |
| :---------- | :------ | :--------------------------- |
| `src`       | string  | Path or URL to Markdown file |
| `container` | Element | Target DOM element           |
| returns     | Promise | Resolves when rendered       |

## Column alignment

Use `:---`, `:---:`, and `---:` in the separator row:

```markdown
| Left      | Center      | Right      |
| :-------- | :---------: | ---------: |
| apple     | banana      | cherry     |
| 1         | 2           | 3          |
```

**Result:**

| Left  | Center | Right  |
| :---- | :----: | -----: |
| apple | banana | cherry |
| 1     | 2      | 3      |

## Cell merging

### Horizontal merge

Write `\|` where you want to extend a cell to the right:

```markdown
| Feature     | lobster.js | Standard MD \|   |
| :---------- | :--------: | :--------------: |
| Tables      | ✓          | ✓                |
| Cell merge  | ✓          | ✗                |
| Warp blocks | ✓          | ✗                |
```

**Result:**

| Feature     | lobster.js | Standard MD \|   |
| :---------- | :--------: | :--------------: |
| Tables      | ✓          | ✓                |
| Cell merge  | ✓          | ✗                |
| Warp blocks | ✓          | ✗                |

### Vertical merge

Write `\---` in a cell to merge it with the cell above:

```markdown
| Browser | Engine    |
| :------ | :-------- |
| Chrome  | Blink     |
| Edge    | \---      |
| Firefox | Gecko     |
| Safari  | WebKit    |
```

**Result:**

| Browser | Engine |
| :------ | :----- |
| Chrome  | Blink  |
| Edge    | \---   |
| Firefox | Gecko  |
| Safari  | WebKit |

### Combined merging

```markdown
| Q1 \|   | Q2      |
| :-----  | :------ |
| Jan     | Apr     |
| \---    | May     |
| Mar     | Jun     |
```

**Result:**

| Q1 \|  | Q2  |
| :----- | :-- |
| Jan    | Apr |
| \---   | May |
| Mar    | Jun |

## Silent table (layout grid)

Prefix each row with `~ ` to create a borderless layout grid. Great for side-by-side comparisons:

```markdown
~ | Left column           | Right column          |
~ | :---                  | :---                  |
~ | Content on the left.  | Content on the right. |
~ | More left content.    | More right content.   |
```

**Result:**

~ | Left column          | Right column          |
~ | :---                 | :---                  |
~ | Content on the left. | Content on the right. |
~ | More left content.   | More right content.   |

Silent tables are the building block for multi-column layouts with **Warp** — see the [Warp / Multi-column](?page=example-warp) page.
