<h1 align="left">Auto-Hashtag-of-Social-Posts</h1>

## Description

Auto-hashtag Service can actively analyze users’ messy input, learn the connection between content and hashtags, and recommend hashtags by understanding the content. What’s more, we use different models for the analysis of different media formats in one twitter and combine the results together using weights, so the system is flexible by modifying the weights when coping with various types of twitter, like sharing a funny picture or make text comments. For more details, see the [full document](https://medium.com/navepnow/auto-hashtag-of-social-posts-4401b8226b87)

## Pipeline

![Pipeline](https://miro.medium.com/max/1400/1*g3qP5ceLOsXlHq6PAJx7_w.png)

## Showcase
![Showcase](https://miro.medium.com/max/1400/1*CYOdCBgpiswrzQYSP9uMqw.jpeg)
## Getting Started
### Install
### Text Analyzer
**1.  [Crawl tweets given multiple hashtags](https://github.com/NavePnow/Auto-Hashtag-of-Social-Posts/blob/master/crawl_tweets.ipynb)**

You should apply for Twitter API and fill the content

    consumer_key = ''
    consumer_secret = ''
    access_token = ''
    access_token_secret = ''

In the expression part, multiple hashtags are used to crawl tweets

    expression = "#friends OR #pets OR #tuesdaymotivation OR #funny OR #contest OR #giveaway OR #ootd OR #win OR #merrychristmas OR #competition OR #fridayfeeling OR #traveltuesday OR #happybirthday OR #wcw OR #goals OR #fitness OR #vegan OR #movies OR #running OR #thankful OR #science OR #blessed OR #influencer OR #metoo"


**2. [Generate Formal Data](https://github.com/NavePnow/Auto-Hashtag-of-Social-Posts/blob/master/Generate_Formal_Data.ipynb)**

In this part, you should specify

    textclassifier = TextClassifier(
    '/content/multi-label-classification', 'dictionary.txt', 'hashtag.txt', 'input.train.text.csv')

the first parameter is working directory, the fourth is crawl data.
[multi-label-classification](https://github.com/NavePnow/multi-label-classification) gives the example of dictionary.txt and hashtag.txt

**3. [Train the model and make prediction](https://github.com/NavePnow/Auto-Hashtag-of-Social-Posts/blob/master/Train_model_and_prediction.ipynb)**

To make a demo, I download my crawled data by

    git clone https://github.com/NavePnow/multi-label-classification.git

you can make your own dataset and train your own model.

### Image Analyzer
All necessary parts are discussed at [Document](https://medium.com/navepnow/auto-hashtag-of-social-posts-4401b8226b87), so you just download the image model and code from Internet. This content is contributed by [XiaoSanGit](https://github.com/XiaoSanGit).


## Usage
clone and repo [auto-hashtag](https://github.com/cs-course-stu/CS4242-Social-Media-Computing-NUS) and modify the model path in

    auto-hashtag/classify/views.py

then run Django on your server

    cd auto-hashtag
    python3 manage.py runserver 8000

## Author

👤 **Evan** - *Text Analyzer*

* Twitter: [@NavePnow](https://twitter.com/NavePnow)
* Github: [@NavePnow](https://github.com/NavePnow)

👤 **XiaoSanGit** - *Image Analyzer*

* Github: [@XiaoSanGit](https://github.com/XiaoSanGit)

## 🤝 Contributing

Contributions, issues and feature requests are welcome!
Feel free to check [issues page](https://github.com/NavePnow/Auto-Hashtag-of-Social-Posts/issues).

## 💰 Show your support

Give a ⭐️ if this project helped you!

| PayPal                                                                                                                                                                       | Patron                                                                                                    |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=DSZJCN4ZUEW74&currency_code=USD&source=url) |   <a href="https://www.patreon.com/NavePnow"> <img src="https://c5.patreon.com/external/logo/become_a_patron_button@2x.png" width="160"> </a>

## 📖 Reference
* [*Twitter_Dictionary_Guide.asp*](https://www.webopedia.com/quick_ref/Twitter_Dictionary_Guide.asp)
* [*op-twitter-abbreviations-you-need-know*](https://www.socialmediatoday.com/content/top-twitter-abbreviations-you-need-know)
* [*top-50-twitter-acronyms-abbreviations-and-initialisms*](https://digiphile.info/2009/06/11/top-50-twitter-acronyms-abbreviations-and-initialisms/)
* [*twitter-dictionary-35-twitter-abbreviations*](https://bitrebels.com/social/twitter-dictionary-35-twitter-abbreviations/)
* [*Train and Deploy the Mighty BERT based NLP models using FastBert and Amazon SageMaker*](https://medium.com/@kaushaltrivedi/train-and-deploy-mighty-transformer-nlp-models-using-fastbert-and-aws-sagemaker-cc4303c51cf3)
* [*fast-bert-github*](https://github.com/kaushaltrivedi/fast-bert)

## 🙏 Acknowledgments
* Advisor: Professor Chua Tat Seng
