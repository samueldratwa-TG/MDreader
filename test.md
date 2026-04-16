# Test Markdown Document

This file tests all the major Markdown features supported by the viewer.

## Text Formatting

This is **bold text**, this is *italic text*, and this is ***bold and italic***. You can also use ~~strikethrough~~.

Here's some `inline code` within a paragraph.

## Links and Images

- [OpenAI website](https://openai.com)
- [Markdown Guide](https://www.markdownguide.org)

## Code Blocks

### JavaScript

```javascript
function fibonacci(n) {
  if (n <= 1) return n;
  return fibonacci(n - 1) + fibonacci(n - 2);
}

const result = fibonacci(10);
console.log(`Fibonacci(10) = ${result}`);
```

### Python

```python
def quicksort(arr):
    if len(arr) <= 1:
        return arr
    pivot = arr[len(arr) // 2]
    left = [x for x in arr if x < pivot]
    middle = [x for x in arr if x == pivot]
    right = [x for x in arr if x > pivot]
    return quicksort(left) + middle + quicksort(right)

print(quicksort([3, 6, 8, 10, 1, 2, 1]))
```

### CSS

```css
.container {
  display: flex;
  gap: 16px;
  align-items: center;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  border-radius: 12px;
  padding: 24px;
}
```

## Tables

| Feature | Status | Notes |
|---------|--------|-------|
| Headings | Done | H1 through H6 |
| Code blocks | Done | With syntax highlighting |
| Tables | Done | With alignment |
| Lists | Done | Ordered and unordered |
| Blockquotes | Done | Nested support |
| RTL/LTR | Done | Per-pane toggle |
| Dark/Light | Done | Global toggle |

### Right-Aligned Table

| Item | Price | Quantity |
|------|------:|:--------:|
| Apples | $1.20 | 5 |
| Bananas | $0.80 | 12 |
| Cherries | $3.50 | 2 |
| **Total** | **$5.50** | **19** |

## Lists

### Unordered List

- First item
- Second item
  - Nested item A
  - Nested item B
    - Deep nested
- Third item

### Ordered List

1. Step one: Open the file
2. Step two: Edit the content
3. Step three: Save the changes
   1. Sub-step: Verify save
   2. Sub-step: Confirm backup

### Task List

- [x] Design the layout
- [x] Implement dark mode
- [ ] Add scroll sync
- [ ] Write documentation

## Blockquotes

> "The only way to do great work is to love what you do."
> — Steve Jobs

> **Nested blockquote example:**
>
> > This is a nested blockquote.
> > It can contain **formatted text** and `code`.

## Horizontal Rules

Above the line.

---

Below the line.

***

Another section.

## HTML in Markdown

<details>
<summary>Click to expand</summary>

This is hidden content that appears when you click the summary.

- Item 1
- Item 2

</details>

## MDX-style JSX Tags

Here are some MDX components that should display as styled tags:

<MyComponent prop="value" />

<Alert type="warning" title="Heads up!" />

<CodeBlock language="typescript">
  const x: number = 42;
</CodeBlock>

## Long Content for Scroll Testing

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo.

Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt.

---

*End of test document*
