# Word to Markdown Converter

A simple, elegant web utility that converts Microsoft Word document content into clean Markdown format. Perfect for technical writers, bloggers, and anyone who needs to convert formatted content from Word to Markdown quickly.

## Features

- **Preserves Formatting**: Maintains headings, bold, italic, links, lists, and other common formatting
- **Cleans Word Junk**: Automatically removes Word's messy HTML, inline styles, mso- classes, and XML metadata
- **Smart Bullet Points**: Detects and converts various bullet characters (•, ●, ○, –, etc.) to proper Markdown lists
- **Live Preview**: Switch between raw Markdown and rendered HTML preview
- **One-Click Copy**: Copy the converted Markdown to your clipboard instantly
- **Download Option**: Save your converted content as a .md file
- **Real-time Stats**: See character, word, and line counts as you work
- **No Installation**: Runs entirely in your browser - no server required

## Usage

1. Open `index.html` in your web browser
2. Copy formatted content from your Word document
3. Paste it into the left text area
4. The converter automatically:
   - Captures Word's HTML formatting
   - Strips out unnecessary markup
   - Converts to clean Markdown
5. View the result in Markdown or Preview tab
6. Click "Copy" to copy to clipboard or "Download .md" to save as a file

## How It Works

The converter uses two powerful libraries:

- **[Turndown.js](https://github.com/mixmark-io/turndown)** - Converts HTML to Markdown
- **[Marked.js](https://marked.js.org/)** - Renders Markdown as HTML for preview

When you paste from Word:
1. The paste event handler captures Word's HTML formatting from the clipboard
2. Custom cleaning functions remove Word-specific markup (mso- classes, inline styles, XML tags)
3. Turndown.js converts the cleaned HTML to Markdown
4. Additional post-processing handles bullet points and line breaks
5. Marked.js renders the preview on demand

## Supported Formatting

- **Headings** (H1-H6)
- **Bold** and *Italic* text
- [Links](https://example.com)
- Bullet lists
- Numbered lists
- Code blocks
- Blockquotes
- Tables (basic)

## Credits

Created by [NotHans](https://nothans.com)
