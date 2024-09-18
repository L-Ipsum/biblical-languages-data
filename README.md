# Biblical Languages Data

A simple dataset of Biblical languages in JSON and CSV formats. This repository uses Strong's Number as the index for the corresponding Greek / Hebrew words. It's ideal for developers, linguists, and researchers working with biblical Greek texts.

## Contents

-   `greek.json`: A JSON file containing the index and Greek words.
-   `greek.csv`: A CSV file containing the index and Greek words.
-   `hebrew.json`: A JSON file containing the index and Hebrew words.
-   `hebrew.csv`: A CSV file containing the index and Hebrew words.

## Overview

This dataset includes:

-   **Strong's Number**: The unique identifier assigned by James Strong, prefixed with "G" for Greek and "H" for Hebrew entries.
-   **Greek Word**: The original Greek word associated with each Strong's number.

### Example Entries

**JSON Format (`greek.json`):**

```json
{
    "G0001": {
        "word": ["Α", "ἄλφα"],
        "transliteration": ["A", "alpha"]
    },
    "G0002": {
        "word": ["Ἀαρών"],
        "transliteration": ["Aaron"]
    },
    "G0003": {
        "word": ["Ἀβαδδών"],
        "transliteration": ["Abaddon"]
    }
    // ... additional entries
}
```

**CSV Format (`greek.csv`):**

```csv
index,transliteration,word
G0001,"A, alpha","Α, ἄλφα"
G0002,Aaron,Ἀαρών
G0003,Abaddon,Ἀβαδδών
// ... additional entries
```

## Usage

You can use this dataset for:

-   Indexing and referencing biblical Greek texts.
-   Developing educational tools for learning Koine Greek.
-   Developing educational tools for learning Biblical Hebrew.
-   Cross-referencing with other biblical resources or lexicons.

### Example in Python

```python
import json

# Load Strong's Greek numbers from JSON file
with open('greek.json', 'r', encoding='utf-8') as f:
    greek_data = json.load(f)

# Access a specific entry
strongs_number = 'G0001'
entry = greek_data.get(strongs_number)
if entry:
    print(f"Strong's Number: {strongs_number}")
    print(f"Greek Words: {entry['word']}")
    print(f"Transliterations: {entry['transliteration']}")
else:
    print(f"Entry {strongs_number} not found.")
```

### Example in CSV

You can open `greek.csv` in any spreadsheet application or process it using libraries like `pandas` in Python.

```python
import pandas as pd

# Load the CSV data
df = pd.read_csv('greek.csv')

# Access entries for a specific Strong's number
strongs_number = 'G0001'
entries = df[df['strongs_number'] == strongs_number]
if not entries.empty:
    greek_words = []
    transliterations = []
    for _, row in entries.iterrows():
        # Split the Greek words and transliterations into lists
        words = row['greek_word'].split(", ")
        translits = row['transliteration'].split(", ")
        greek_words.extend(words)
        transliterations.extend(translits)
    print(f"Strong's Number: {strongs_number}")
    print(f"Greek Words: {greek_words}")
    print(f"Transliterations: {transliterations}")
else:
    print(f"Entry {strongs_number} not found.")
```

## License

This work is licensed under the [Creative Commons Attribution 4.0 International License](LICENSE).

© Daniel Sperinck, 2024

## Attribution

-   **James Strong**, _Strong's Exhaustive Concordance of the Bible_ (1890). The original work is in the public domain.
-   If you use this dataset, please provide appropriate credit by linking back to this repository or mentioning the source in your work.

---

When using this dataset, please attribute it as follows:

-   **Dataset Title**: Biblical Languages Data
-   **Author**: Daniel Sperinck
-   **Year**: 2024
-   **License**: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
-   **Source**: [Link to the GitHub repository](https://github.com/yourusername/your-repo-name)

## Contributing

Contributions are welcome! If you'd like to enhance this dataset or fix any issues, please:

1. Fork the repository.
2. Create a new branch for your changes.
3. Submit a pull request with a detailed description of your changes.

## Contact

If you have any questions or suggestions, feel free to open an issue.

## Disclaimer

While the original Strong's numbers are in the public domain, this compiled dataset and any additional content are licensed under CC BY 4.0. Ensure compliance with the license when using this dataset.

---

**Note:** This dataset now includes Strong’s numbers as indexes, the corresponding Greek words, and their transliterations. Each Strong’s number may have multiple Greek words and transliterations associated with it. Definitions, pronunciations, or additional lexical information are not yet included. If you require more comprehensive data, feel free to open an issue or consider integrating this dataset with other resources or lexicons that provide detailed entries.
