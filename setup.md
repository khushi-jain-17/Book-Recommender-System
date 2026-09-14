pip install -r requirements.txt
pip install ipykernel
python -m ipykernel install --user --name=book-recommender --display-name "Python (book-recommender)"



# Build a Semantic Book Recommender with LLMs 

1. Clean the data
It starts with a big dataset of books (titles, descriptions, etc.) pulled from Kaggle. This step tidies it up — fixing missing values, weird formatting, etc. — so it's usable.

2. Semantic search (the "smart search" part)
Normally, if you search "revenge story," a basic search engine looks for books with the literal words "revenge" or "story" in them. This project instead converts each book's description into a set of numbers (called an "embedding") that captures its meaning. It stores all these in a special database (a "vector database"). So when you type something like "a book about a person seeking revenge," it finds books that match that idea, even if they don't use those exact words.

3. Fiction vs. non-fiction tagging
It uses an LLM (large language model) to automatically read each book's description and decide whether it's fiction or non-fiction — without needing anyone to manually label thousands of books. This is called "zero-shot classification" (the model wasn't specifically trained on this task, but can still do it reasonably well).

4. Emotion/tone detection
Similarly, it uses an LLM to scan the text and figure out the emotional tone of each book — how joyful, sad, suspenseful, etc. it feels. This lets users later filter or sort books by mood.

5. The actual app
Finally, all of this is wrapped into a simple web app (built with Gradio, a tool for quickly making interactive UIs). A user can type a natural-language query, optionally filter by fiction/non-fiction or by emotional tone, and get book recommendations that actually match what they meant.

In short: A "smart" book recommender — one that understands intent and emotional tone — using embeddings, vector search, and LLMs, all wrapped in a simple web interface. It's a good practical example of how modern AI search/recommendation systems work under the hood.

