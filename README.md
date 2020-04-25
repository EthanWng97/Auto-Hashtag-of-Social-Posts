# Auto-Hashtag-of-Social-Posts
Auto-hashtag Service can actively analyze users’ messy input, learn the connection between content and hashtags, and recommend hashtags by understanding the content. What’s more, we use different models for the analysis of different media formats in one twitter and combine the results together using weights, so the system is flexible by modifying the weights when coping with various types of twitter, like sharing a funny picture or make text comments. For more details, see the [full document](https://medium.com/navepnow/auto-hashtag-of-social-posts-4401b8226b87)

## Pipeline

![Pipeline](https://cdn.jsdelivr.net/gh/NavePnow/blog_photo@private//Untitled.png)

## Showcase
![Showcase](https://cdn.jsdelivr.net/gh/NavePnow/blog_photo@private//un123.jpg)
## Getting Started
### Installing
### Text Analyzer
**1.  [Crawl tweets given multiple hashtags](https://github.com/NavePnow/Auto-Hashtag-of-Social-Posts/blob/master/crawl_tweets.ipynb)**

You should apply for Twitter API and fill the content

```
consumer_key = ''
consumer_secret = ''
access_token = ''
access_token_secret = ''
```

In the expression part, multiple hashtags are used to crawl tweets

```
expression = "#friends OR #pets OR #tuesdaymotivation OR #funny OR #contest OR #giveaway OR #ootd OR #win OR #merrychristmas OR #competition OR #fridayfeeling OR #traveltuesday OR #happybirthday OR #wcw OR #goals OR #fitness OR #vegan OR #movies OR #running OR #thankful OR #science OR #blessed OR #influencer OR #metoo"
```

**2. [Generate Formal Data](https://github.com/NavePnow/Auto-Hashtag-of-Social-Posts/blob/master/Generate_Formal_Data.ipynb)**

In this part, you should specify

```
textclassifier = TextClassifier(
    '/content/multi-label-classification', 'dictionary.txt', 'hashtag.txt', 'input.train.text.csv')
```

the first parameter is working directory, the fourth is crawl data.
[multi-label-classification](https://github.com/NavePnow/multi-label-classification) gives the example of dictionary.txt and hashtag.txt

**3. [Train the model and make prediction](https://github.com/NavePnow/Auto-Hashtag-of-Social-Posts/blob/master/Train_model_and_prediction.ipynb)**

To make a demo, I download my crawled data by
```
git clone https://github.com/NavePnow/multi-label-classification.git
```
you can make your own dataset and train your own model.

### Image Analyzer
All necessary parts are discussed at [Document](https://medium.com/navepnow/auto-hashtag-of-social-posts-4401b8226b87), so you just download the image model and code from Internet. This content is contributed by [XiaoSanGit](https://github.com/XiaoSanGit).


## Running the tests
clone and repo [auto-hashtag](https://github.com/cs-course-stu/CS4242-Social-Media-Computing-NUS) and modify the model path in
```
auto-hashtag/classify/views.py
```
then run Django on your server
```
cd auto-hashtag
python3 manage.py runserver 8000
```

## Authors
* **[NavePnow](https://github.com/NavePnow)** - *Text Analyzer*
* **[XiaoSanGit](https://github.com/XiaoSanGit)** - *Image Analyzer*