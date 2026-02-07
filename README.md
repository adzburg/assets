# Bible Data Files

This directory should contain Bible JSON files for each translation.

## File Format

Each translation should be a JSON file named `{translation}.json` (e.g., `kjv.json`, `web.json`, `bbe.json`).

### Structure

The JSON file should follow this structure:

```json
{
  "Genesis": {
    "1": {
      "1": "In the beginning God created the heaven and the earth.",
      "2": "And the earth was without form, and void; and darkness was upon the face of the deep. And the Spirit of God moved upon the face of the waters.",
      "3": "And God said, Let there be light: and there was light."
    },
    "2": {
      "1": "Thus the heavens and the earth were finished, and all the host of them."
    }
  },
  "Exodus": {
    "1": {
      "1": "Now these are the names of the children of Israel, which came into Egypt..."
    }
  }
}
```

### Format Rules

- **Book names**: Must match exactly the Book type in `types/verse.ts`
- **Chapters**: String keys (e.g., "1", "2", "3")
- **Verses**: String keys (e.g., "1", "2", "3")
- **Text**: Plain string, no verse numbers included

### Example Book Names

Use these exact names (case-sensitive):
- Genesis, Exodus, Leviticus, Numbers, Deuteronomy
- Joshua, Judges, Ruth, 1 Samuel, 2 Samuel
- 1 Kings, 2 Kings, 1 Chronicles, 2 Chronicles, Ezra
- Nehemiah, Esther, Job, Psalms, Proverbs
- Ecclesiastes, Song of Solomon, Isaiah, Jeremiah, Lamentations
- Ezekiel, Daniel, Hosea, Joel, Amos
- Obadiah, Jonah, Micah, Nahum, Habakkuk
- Zephaniah, Haggai, Zechariah, Malachi
- Matthew, Mark, Luke, John, Acts
- Romans, 1 Corinthians, 2 Corinthians, Galatians, Ephesians
- Philippians, Colossians, 1 Thessalonians, 2 Thessalonians
- 1 Timothy, 2 Timothy, Titus, Philemon, Hebrews
- James, 1 Peter, 2 Peter, 1 John, 2 John
- 3 John, Jude, Revelation

## Where to Get Bible Data

### Recommended: jadenzaleski/bible-translations

The easiest way is to use the [jadenzaleski/bible-translations](https://github.com/jadenzaleski/bible-translations) repository:

1. **Clone the repository** and use their Python script to generate JSON files
2. **Use the conversion script** in `scripts/convert-bible-format.py` to convert to our format
3. **See `scripts/README.md`** for detailed instructions

This repository supports:
- ✅ **KJV** (King James Version) - Public Domain
- ✅ **WEB** (World English Bible) - Public Domain
- ✅ **ASV** (American Standard Version) - Public Domain
- ✅ **YLT** (Young's Literal Translation) - Public Domain

### Other Public Domain Sources

1. **King James Version (KJV)**
   - Public domain
   - Available from various sources

2. **World English Bible (WEB)**
   - Public domain
   - Available at: https://ebible.org/

3. **Bible in Basic English (BBE)**
   - Public domain
   - Available from various sources

### Conversion Tools

Use `scripts/convert-bible-format.py` to convert Bible JSON from other formats to the required structure.

## File Size

Bible JSON files are large (several MB each). Make sure to:
- Add them to `.gitignore` if they're too large for git
- Or use Git LFS for version control
- Consider compressing or splitting if needed

## Testing

Once you add a Bible JSON file, the app will automatically load it when you select that translation. Test by:
1. Adding `kjv.json` to this directory
2. Running the app
3. Selecting KJV translation in settings
4. Verifying verses load correctly
