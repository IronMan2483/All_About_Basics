# __Wordcloud__

## __Terminal__

````````
pyenv local 3.9.4

python -m venv .venv

source .venv/bin/activate

pip install --upgrade pip

pip install wordcloud

`````````

---

## __VSC/Jupyter Notebook__

### __OPTION1__

`
  from wordcloud import WordCloud, STOPWORDS
`

<br />

````
comment_words = '' 

stopwords = set(STOPWORDS)

stopwords = ['nan', 'NaN', 'Nan', 'NAN'] + list(STOPWORDS)

data = df_dataset_name['column1'].value_counts().to_dict()

wc = WordCloud().generate_from_frequencies(data)

plt.figure(figsize=(10,6), facecolor="black") 

plt.imshow(wc)

plt.axis('off')

plt.show()

``````````

---

### __OPTION2__

```````
text = " ".join(review for review in df_dataset_name.column1)

print ("There are {} words in the combination of all review.".format(len(text)))

stopwords = set(STOPWORDS)

stopwords.update(["na",'Na', 'nA', 'NA', 'none'])

wordcloud_searchpath = WordCloud(stopwords=stopwords, background_color="white").generate(text)

plt.figure(figsize=(10,6), facecolor="black") 

plt.imshow(wordcloud_searchpath, interpolation='bilinear')

plt.axis("off")

plt.show()

`````````

* facecolor="black" is here the black frame of the wordcloud
* background_color="white" is the background color of the wordcloud

<br />

---

## __Wordcloud in an image - example with an US flag__

source: https://www.datacamp.com/community/tutorials/wordcloud-python

1. Generate a word cloud image
```
mask = np.array(Image.open("img/us.png"))

wordcloud_usa = WordCloud(stopwords=stopwords, background_color="white", mode="RGBA", max_words=1000, mask=mask).generate(usa)
```

2. create coloring from image
```````
image_colors = ImageColorGenerator(mask)

plt.figure(figsize=[7,7])

plt.imshow(wordcloud_usa.recolor(color_func=image_colors), interpolation="bilinear")

plt.axis("off")
```````

3. store to file
```
plt.savefig("img/us_wine.png", format="png")

plt.show()

```
