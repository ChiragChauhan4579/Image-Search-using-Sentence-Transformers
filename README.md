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

    embeddings can be performed using the < .encode< function

```
img_emb = model.encode()
```

