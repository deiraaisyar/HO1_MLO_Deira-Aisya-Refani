# edX Scrapping & Preprocessing Project
by: Deira Aisya Refani

📚 edX Scraping & Preprocessing Project
This project focuses on scraping online course data from edX using the official Algolia-based API through Python's requests module. The goal is to collect structured and comprehensive course metadata that can later be used for educational data analysis, recommendation systems, or dashboard visualizations.

🔍 Features
Retrieves course information such as:

- Title
- Partner/University
- Descriptions (primary, secondary, tertiary)
- Availability
- Subject and Level
- Language
- Program Type and Product
- Course Duration 
- Skills and Staff
- Translation & Transcription Language
- Enrollment count
- Marketing URL
- Extracts data across all pages using Algolia's pagination system.
- Saved as a structured CSV file for further processing.
- Preprocessing such as text normalization (e.g., lowercasing, stopword removal) is done separately.

🧹 Text Preprocessing
After scraping, selected columns undergo structured text preprocessing to clean and normalize the data before vectorization and downstream NLP tasks.

🔧 Preprocessing Steps (Full Pipeline)
The following transformations are applied only to selected text-based columns (title, primary_description, secondary_description, tertiary_description, and skill) to prepare them for vectorization:
- Remove HTML tags – Strip any embedded HTML elements (e.g., <b>, <br>) from descriptions.
- Lowercasing – Convert all text to lowercase to ensure uniformity.
- Remove punctuation & special symbols – Keep only alphanumeric characters and whitespace.
- Stopword removal – Remove common English stopwords such as "the", "and", "is", etc.
- Lemmatization – Reduce words to their base or dictionary form (e.g., “running” → “run”, “better” → “good”).

📌 Partially Preprocessed Columns
Other text-based fields such as:
- partner
- level
- language
- program_type
- product
- availability
- subject
- staff
- translation_language
- transcription_language

…are only lightly cleaned (e.g., lowercased or left as-is) to preserve label-level structure, as they are not intended for direct vectorization.

🚫 Non-Processed Columns
Some columns such as marketing_url are intentionally left untouched because they are identifiers or external references, not natural language content.

⚠️ Missing Value Handling
Missing values are not handled yet in this stage.

This is intentional, as handling strategies (e.g., imputation, removal, or flagging) are highly dependent on the final objective, whether it's classification, recommendation, clustering, or visualization. Final decisions will be made once the analysis direction is finalized.

📁 Output
Cleaned dataset exported as edx_courses.csv, ready for NLP preprocessing or data analysis tasks.