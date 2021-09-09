<img width="850" src="https://user-images.githubusercontent.com/80333521/131840039-24630bbe-d5c1-4237-9406-380ec6c49451.png">

# HK WhiskyNav
- An all-in-one application built to accompany users from knowing whisky to taking one (or more) bottle(s) of whisky into their life!
- A built-from-scratch but comprehensive application incorporating different data science and machine learning techniques, including web-scraping, data visualization, natural language processing, machine learning, deep learning and recommendation system.
- A 3-week Capstone project for a team of 4 human beings to showcase what we have learnt in the Bootcamp!
<br><br />
## Final product 

- 2 pathways for input
<img width="695" alt="pathways" src="https://user-images.githubusercontent.com/80333521/131826472-12a2adce-d5e7-466d-bff1-2f586608223d.png">

- Live demonstration

https://user-images.githubusercontent.com/80333521/131822984-9f72f09e-22e3-4678-93d0-73cea744e26b.mp4

<br><br />
## The Building Process
We have split the whole development of application into 3 episodes.

<img width="695" src="https://user-images.githubusercontent.com/80333521/131829517-5e46525b-edc7-49e0-a6b9-cda90e6dc38b.png">

<br><br />
## Episode 1 - Data Collection
### Data to be collected:
<img width="695" src="https://user-images.githubusercontent.com/80333521/131839323-5287f781-42e5-42fa-ac44-782484d8cb1f.png">

#### 1. Top 100 whisky
To have a reasonable scope and complexity for this 3 week project, we chose to focus only on the Top 100 whisky from Whisky.com. We then performed web-scraping to obtain the distillery name, year and ranking of that whisky from the website, with duplicated and unnecessary data being removed using regex.

<img width="695" src="https://user-images.githubusercontent.com/80333521/131842513-36bb2b81-d160-4e1d-8c71-f6f54c603f7d.png">

#### 2. Whisky images
To train our model for whisky recognition, we downloaded 20 to 30 images for each whisky from Google.
<img width="695" src="https://user-images.githubusercontent.com/80333521/131846020-d4533fc5-fc29-436c-a41c-b705c2ca6b6a.png">


#### 3. Whisky flavour profile
To have a flavour analysis on whisky, we web-scraped the tasting notes given by whisky expert in the International Whisky Community and reviews from the general public.
<img width="695" src="https://user-images.githubusercontent.com/80333521/131846860-df441868-2834-4fab-aa15-9780d5b73e24.png">

#### 4. Availability in Hong Kong
To have a thorough whisky availability and price data, we web-scraped for the whisky info, price and selling locations from three major online retailers and platforms in Hong Kong (Watson's Wine, HK Liqour Store & Price.com). We then consolidated, cleansed and visualized the data using histogram and a URL linked to the address.

<img width="695" src="https://user-images.githubusercontent.com/80333521/131852880-41343aed-1896-4738-a036-17514fad8d1a.png">

<br><br />
## Episode 2 - Image Recognition
At first, we proposed to use OpenCV EAST and Tesseract for the text detection and recognition on the label of a whisky bottle. 
However, it failed to locate and identify the text even with only a mild divergence from a plain, clear image.

<img width="695" src="https://user-images.githubusercontent.com/80333521/131951494-1556bb8c-f82f-4162-8afc-27617b505cd7.png">

Therefore, we changed our approach. We instead chose to use Convolutional Neural Network (CNN) for feature extraction on the image that contains a whole whisky bottle and customized an additional layer to replace the classification layer originally included in InceptionV3 for identifying our 100 different brands and years of whiskies.

<img width="695" src="https://user-images.githubusercontent.com/80333521/131958717-bc64455c-44f5-49c4-a3e2-0bee6c2c96e1.png">
<img width="695" src="https://user-images.githubusercontent.com/80333521/131958620-195e3035-566b-4d89-b896-534e27b71359.png">
<img width="695" src="https://user-images.githubusercontent.com/80333521/131959117-5cf46842-9367-42f9-9f23-ed41e1fe48ac.png">

The 57% accuracy achieved by this approach is not satisfactory, notwithstanding the long hours spent on training this model. 

To improve the model, we fine-tuned it by making a few adjustments:
- Cropped out only the bottles of whisky (eliminate the noisy background)
<img width="695" src="https://user-images.githubusercontent.com/80333521/131960279-01fbafa6-daf9-4716-a576-959a96bc730f.png">

- Augmented the images with random effects and random magnitude for each image
<img width="695" src="https://user-images.githubusercontent.com/80333521/131960316-d95e47ef-eadc-401f-89d7-3ebf3b03bace.png">

- Fed the model with non-whisky classes
<img width="695" src="https://user-images.githubusercontent.com/80333521/131960361-24d7ac59-6162-4077-a555-8a4023073fe2.png">

Fortunately, we achieved a better result with a much higher accuracy.
<img width="695" src="https://user-images.githubusercontent.com/80333521/131962436-cc43f336-3c67-4f41-bf96-9658647fe64e.png">

By reducing the learning rate and cutting the batch size by half whenever the accuracy plateaued (i.e. the green lines on the graph), it was to assist the model to find the steepest descent and to achieve greater accuracy.

###### **After the completion of this project, we learnt that there were data leakage during the training which would result in close training and validation accuracy. Luckily, it does not have adverse effects on the recognition and the implementation of it on our application. However, here is one of the most important lesson learnt to guide us to have thought more precisely in the future.*

### Implementation of the model
<img width="695" src="https://user-images.githubusercontent.com/80333521/131966854-b1010d78-1d70-4212-92e6-fba9bfebf33b.png">
<img width="695" src="https://user-images.githubusercontent.com/80333521/131966907-951d1e56-e3b1-43f0-8907-87619ca4605d.png">
<img width="695" src="https://user-images.githubusercontent.com/80333521/131966806-8ffbd49f-d525-4a73-a597-f33ff1a6b15b.png">
<img width="695" src="https://user-images.githubusercontent.com/80333521/131966947-f5741f24-7e28-455a-92a9-7f4b6c86476a.png">

<br><br />
## Episode 3 - Flavour Analysis & Recommendation System
### A ) Flavour Profile Analysis
To be able to provide a customized whisky recommendation for users, one must have a common ground about the taste or flavour of the whisky for users to communicate what they like or their preference upon choosing one whisky back home. 

<img width="695" src="https://user-images.githubusercontent.com/80333521/131978249-4cda096e-622b-4471-98b2-b04d109c8c55.png">

Researches had found that 12 flavours are sufficient for describing the taste of all available whiskies in the market. BINGO! We trust these masters and web-scraped the whisky flavour profile database (see below) for building our one-of-a-kind whisky recommendation system next.

<img width="695" src="https://user-images.githubusercontent.com/80333521/131978319-9a1325a0-17f9-4a0f-81ca-21953e0e4c8e.png">

To minimize the efforts our app users need to communicate their preference on whisky, Principal Component Analysis (PCA) is used to find out the minimum number of adjective that is able to describe utmost variance.
<img width="695" src="https://user-images.githubusercontent.com/80333521/132619747-aca300c0-96aa-4015-972c-8ed2011f0692.png">

However, the result showed that in order to explain 95% of variance, we need at least 10 components. Since this does not match our expectation of keeping the number of choices practical and hassle-free for users to choose from, we changed our approach again. 

We preserved all 12 components, while extracting 4 most important flavours and setting the other 8 flavours as default value for both firstcomers and dedicated users to describe their preferred taste and enjoy a customized degree of customization. The question is how we do it? 

<img width="695" src="https://user-images.githubusercontent.com/80333521/132621366-3d142174-e852-477e-86e8-39a60807a3e5.png">

As we didn't have the clustering label for all whiskies, we took a two-step approach. First, we used kMeans to figure out the label, then we used Logistic Regression to find out the feature importance of all 12 adjectives (flavours). The result of the kMeans clustering combined with elbow method suggested that it is at best to have 4 adjectives for clustering. What come next is: which 4 flavours to represent?

<img width="695" src="https://user-images.githubusercontent.com/80333521/132635164-9970a24d-3175-40a5-81df-b532070f513d.png">

The correlation matrix (on the left) and the coefficient (on the right) of all adjectives showed us some hints in choosing for our finale:
- "Winey" & "Honey" - the 2 most powerful (positive) adjectives
- "Smokey" - the most powerful (negative) adjectives
- "Fruity" - low correlation and more relatable than others

### B ) Recommendation System
According to the whisky-lover of our team, presence of a flavour is much more important than the intensity of it. This very much affect which measure to choose for our recommendation system.

<img width="695" src="https://user-images.githubusercontent.com/80333521/132638544-d8fbd7a6-b48e-407c-8bf6-3301c5582993.png">

From above, whisky 1 and 3 are smoky, while whisky 2 is a fruity one. Euclidean Distance would tell us whisky 2 and 3 are similar, while Cosine Distance would tell us whisky 1 and 3 are similar. For the case of whisky recommendation, we chose Cosine Distance as our metric to better match users' expectation.

<img width="695" src="https://user-images.githubusercontent.com/80333521/132642837-3ca55d7e-f655-4349-8ba7-81755f729c5a.png">

To provide a flavour description of whisky, we consolidated and web-scraped thousands of customer reviews of each whisky online and generated a Word Cloud using tf-idf, with all stop words filtered out. This allow our users to have a vivid imagination about the taste of the whisky simply by looking at the Word Cloud.

### C ) Consolidation and App Development

<img width="695" src="https://user-images.githubusercontent.com/80333521/132644061-224baf21-bbad-4ebb-bb69-0687d81a78d3.png">

<br><br />
## Challenges
<img width="695" src="https://user-images.githubusercontent.com/80333521/132647322-855f38a1-fcc8-4864-a8cf-bbc967fa5b73.png">

<br><br />
## Next Steps
<img width="695" src="https://user-images.githubusercontent.com/80333521/132647621-dce5d28d-18ab-4b10-b2ec-a655b5661aac.png">
