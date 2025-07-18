# N8N Posts and Comments Data Processing Workflow

## 📌 Workflow Overview
This workflow retrieves posts (IDs 1 to 10) from `https://jsonplaceholder.typicode.com/posts/{id}` and their corresponding comments. It processes each post and comment, applies cleaning and data enrichment rules (title casing, body truncation, keyword extraction, category assignment, etc.), and merges them into a unified JSON structure before storing them in a Google Sheet.

---

## ⚙️ How to Import and Run

1. Open your N8N instance.
2. Go to **Workflows** → **Import from File**.
3. Upload the provided `workflow.json`.
4. Configure Google Sheets credentials (OAuth or API Key).
5. Connect the Google Sheets node to your preferred spreadsheet.
6. Click **Execute Workflow**.

---

## 🗂️ Database Information

- **Platform**: Google Sheets
- **Access Type**: View-only link
- **Access Link**: [Google Sheet View Link](https://docs.google.com/spreadsheets/d/1wgPfYk8TYXl1eX2gaC4YW4by9wpTnRatFuG7tV8ztDI/edit?usp=sharing)
  
> **Note**: For a production-grade implementation, a better choice would be **MongoDB Atlas** due to its structured storage, query capabilities, and scalability.  
For the sake of simplicity and faster setup, Google Sheets was used in this evaluation task.
---

## 📝 Sample Output (JSON Structure)

```json
{
    "record_id": "POST_001",
    "content": {
        "title": "Sunt Aut Facere Repellat Provident Occaecati Excepturi Optio Reprehenderit",
        "body": "quia et suscipit suscipit recusandae consequuntur expedita et cum reprehenderit molestiae ut ut quas...",
        "word_count": 23,
        "category": "medium",
        "keywords": [
            "sunt",
            "aut",
            "facere"
        ]
    },
    "metadata": {
        "original_id": 1,
        "processed_date": "2025-07-18",
        "status": "needs_review",
        "tags": [
            "processed",
            "latin",
            "long_title"
        ],
        "processing_steps": [
            "title_cleaned",
            "body_truncated",
            "keywords_extracted",
            "category_assigned"
        ]
    },
    "analytics": {
        "title_length": 74,
        "body_length": 103,
        "has_long_title": true,
        "common_words": [
            "the",
            "and",
            "of"
        ]
    },
    "comments": [
        {
            "comment_id": 1,
            "email": "Eliseo@gardner.biz",
            "short_body": "laudantium enim quasi est quidem magnam voluptate ...",
            "body_length": 148,
            "status": "invalid",
            "keywords": [
                "laudantium",
                "enim"
            ]
        },
        {
            "comment_id": 2,
            "email": "Jayne_Kuhic@sydney.com",
            "short_body": "est natus enim nihil est dolore omnis voluptatem n...",
            "body_length": 168,
            "status": "invalid",
            "keywords": [
                "est",
                "natus"
            ]
        },
        {
            "comment_id": 3,
            "email": "Nikita@garfield.biz",
            "short_body": "quia molestiae reprehenderit quasi aspernatur\naut ...",
            "body_length": 218,
            "status": "valid",
            "keywords": [
                "quia",
                "molestiae"
            ]
        },
        {
            "comment_id": 4,
            "email": "Lew@alysha.tv",
            "short_body": "non et atque\noccaecati deserunt quas accusantium u...",
            "body_length": 154,
            "status": "invalid",
            "keywords": [
                "non",
                "et"
            ]
        },
        {
            "comment_id": 5,
            "email": "Hayden@althea.biz",
            "short_body": "harum non quasi et ratione\ntempore iure ex volupta...",
            "body_length": 132,
            "status": "valid",
            "keywords": [
                "harum",
                "non"
            ]
        }
    ]
}
