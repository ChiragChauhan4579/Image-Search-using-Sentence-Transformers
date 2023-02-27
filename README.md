# Image-Search-using-Sentence-Transformers

1) Download the library
```
pip install sentence_transformers
```

2) Then load all the necessary libraries and download the Clip model that can be used for image search.

```
model = SentenceTransformer('clip-ViT-B-32')
```

3) Generate vector embeddings of all the images

    embeddings can be performed using the `.encode` function

```
img_emb = model.encode()
```

4) Define the search function to match the embedding vectors of text query and different images

```
def search(query, k=1):
    query_emb = model.encode([query], convert_to_tensor=True, show_progress_bar=False)
    
    hits = util.semantic_search(query_emb, img_emb, top_k=k)[0]
    
    print("Query:")
    display(query)
    for hit in hits:
        print(img_names[hit['corpus_id']])
        display(IPImage(os.path.join(img_folder, img_names[hit['corpus_id']]), width=500,height=500))
```

5) Give any text query to the search function to generate the image. You can change the value of K to generate more images from the query.

```
search(query)
```
