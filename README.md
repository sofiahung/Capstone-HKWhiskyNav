<img width="850" src="https://user-images.githubusercontent.com/80333521/131840039-24630bbe-d5c1-4237-9406-380ec6c49451.png">

# HK WhiskyNav
- An all-in-one application built to accompany users from knowing whisky to taking one (or more) bottle(s) of whisky into their life!
- A built-from-scratch but comprehensive application incorporating different data science and machine learning techniques, including web-scraping, data visualization, natural language processing, machine learning, deep learning and recommendation system.
- A 3-week Capstone project for a team of 4 human beings to showcase what we have learnt in the Bootcamp!


## Final product 

- 2 pathways for input
<img width="695" alt="pathways" src="https://user-images.githubusercontent.com/80333521/131826472-12a2adce-d5e7-466d-bff1-2f586608223d.png">

- Live demonstration

https://user-images.githubusercontent.com/80333521/131822984-9f72f09e-22e3-4678-93d0-73cea744e26b.mp4

## The Building Process
We have split the whole development of application into 3 episodes.

<img width="695" src="https://user-images.githubusercontent.com/80333521/131829517-5e46525b-edc7-49e0-a6b9-cda90e6dc38b.png">


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
To have a thorough whisky availability and price data, we web-scraped for the whisky info, price and selling locations from three major online retailers and platforms in Hong Kong (Watson's Wine, HK Liqour Store & Price.com). We then cleansed the data and visualized it using histogram and a URL linked to the address.
<img width="695" src="https://user-images.githubusercontent.com/80333521/131852880-41343aed-1896-4738-a036-17514fad8d1a.png">


## Episode 2 - Image Recognition



## Episode 3 - Flavour Analysis & Recommendation System
