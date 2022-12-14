# Predicting-Success-on-Youtube

### Background  
I chose to center my final project around a passion project I have been working on for the last 6 months, launching a Youtube series. In October of this year, my best friend and I will be launching an animated series of comedic shorts on social media called "Dota Shorts." 
My friend and I have always had a passion for filmmaking and decided it was time to stop talking about "one day" and just make it happen.

### Initial Target - Is the video successful or not?
For this project, we define success as each video generating enough revenue to cover the cost of itself. As this is a passion project, making a profit would be wonderful, but it is not necessary. As long as the video's are self sustainable, we will be able to continue making more. Our measure of success would then be a goal of +60,000 views per video. At the typical rate of $.035 a view, this would be enough to cover the costs of each video.

##### Code for instantiating the "Is_Successful" column.
                Is_Successful = []
        for view in list(range(0,len(US_vids))):
            if views[view] > 180000:
                    Is_Successful.append(True)
            else:
                    Is_Successful.append(False)
        US_vids['Is Successful'] = Is_Successful:
       
This presents an issue when looking at our data as the data is somewhat skewed. Since the dataset only includes videos that were trending, it is safe to assume that certain features (views, likes, dislikes, comments, etc..) are weighted significantly higher on average than they would be for a typical random assortment. 
This is simply a limitation for our data, and in response we chose to triple the number of views needed to be 'successful' from +60,000 to +180,000 views in order to provide our prediction model, less weighted data. Before this change, our modeless baseline was 96% accurate when predicting success for each video.

### Data from Kaggle 
For this project, I chose to first look into Youtube data that I found on the Kaggle website. The data set included 40,000 different YouTube videos that had 'trended' over the span of +210 days (2017-2018). We used this data to create a prediction model in hopes of learning which factors are directly related to a Youtube Channel's success. Unfortunately, we discovered that there is no metric (# of tags in the video, length of description, genre) within the creators control that directly affects the success of a video. But this doesn't mean we didn't find anything useful. 
  ##### Link to dataset - https://www.kaggle.com/datasets/pavandas/youtube

### Modeling 
Our Decision Tree model suggests that likes, dislikes and comments are the only major components that directly effect the number of views your video gets. This is consistent with the fact that 'trending videos' become so by a statistical algorithm designed by google. This tells us it is the social component of the video that will decide its fate. Does it facilitate interaction and discussion? It is important to note that dislikes were also positively correlated with a video's success. Once again reinforcing the notion that you don't need to make a video that everyone will like, you need to make one that entices people into interaction and discussion.

### NLP - Top words in Tags and Titles
As said before, the model suggests that there is no metric (# of tags in the video, length of description, genre) within the creators control that significantly affects the success of a video. So we asked ourselves, what else can we control? Well, the number of tags may not useful, but the 'right' tags might be of value. So, we checked the data for the most commonly used tags throughout the dataset. The top three tags used are 'Official', 'New', and 'Trailer'. Buzzwords that can validate the content and build anticipation. 

##### Top words in titles across all catagories 
![download](https://user-images.githubusercontent.com/84747768/183953862-077095db-3aa1-4cc2-b65a-535fa5272151.png)
##### Top words in titles for Film and Animation
![download](https://user-images.githubusercontent.com/84747768/183954767-9ff04590-1fd4-4a3c-af3d-cccf8a621512.png)

### finding a new and improved approach to the business problem -- Scraping Dota 2 data 
People like New content, but they want that content to be informed (Official) and they would like to know what's coming before it arrives (Trailer). This leads me to believe that creating a trailer/advertisement for our series is a smarter strategy than releasing them out of the blue.

Lastly, we asked ourselves when should the series be released. To answer this question, we scraped data off of the Twitch website. Twitch is one of the top live video game streaming sites out there. Millions of people watch video game tournaments and individual professionals play video games every single day using this site. We specifically looked at the monthly viewership statistics of the video game "Dota 2", the subject of our YouTube series. We wanted to look at the last four years to see viewership trends in order to determine a release date. The data provided us with a clear and obvious answer. Every year, there is a 1.5-2 month period in which viewership skyrockets by anywhere between 3-6 times the average. This increase is in response to the annual Dota International Tournament (also referred to as TI), the biggest video game tournament in the world. This year in October, "TI" will take place in Singapore with an estimated prize pool of 45 million dollars. Our greatest chance of creating an animated YouTube series of comedic shorts about the game of Dota 2 is releasing the series during this window.

### Recomendations     
   To summarize, our analysis of the Youtube and Twitch Data leads us to make 3 recommendations to Dota Shorts:
1. We recommend each episode contain content that facilitates and entices the viewer to interact with the video and discussion with other players and fans. Differeintiating opinions are good for dissucusion.
![download](https://user-images.githubusercontent.com/84747768/183951884-ef551d3f-4541-4f29-a0a8-7a8c3dbe117a.png)
![download](https://user-images.githubusercontent.com/84747768/183952308-aab880f7-8e14-48c5-bfd5-38408adb33ff.png)
![download](https://user-images.githubusercontent.com/84747768/183952495-d9094540-79ed-4990-a6d9-d24ae3727558.png)
##### here we see the Non-profit and activism is the most popular catagory for likes,dislikes,and comments (per view) on it's videos. This happens because it has controversial topics and disscussions. It could be beneficial to implement a similar trend to our Dota 2 videos.  
2. We recommend releasing a trailer advertising the series a few weeks before the series to build anticipation. This should not require additional funds to achieve if you can simply cut together a few random moments from the series with a VoiceOver you write and record yourself.
3. We highly recommend the series be release throughout the month of October while the Dota International is taking place. The increased viewership will provide the series the best opportunity for success.

# [Slides](Presentation.pdf)
# Thank You

github(1): kinghenderson

github(2): rgthomps
         
Repository Structure:

    ????????? exploritory                                # folder containing non-important notebooks 
       -Notebook
       -Youtube_project_king.ipynb
    ????????? .gitignore                                 # images and graphics used in project
    ????????? Final Notebook                             # code/project notebook
    ????????? Presentation.pdf                           # non-technical stakeholder presentation slides
    ????????? README.md                                  # the top-level README for reviewers of this project         
