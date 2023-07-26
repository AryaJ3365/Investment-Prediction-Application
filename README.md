## **How does the process actually work?**

1.  **Take our dataset then transform it to make it readable by our ML model**
    1.  This is done by dropping columns that aren't readable or unnecessary in determining a grade for the venture.
    2.  Also, by using standard scaler which allows us to take columns and change it into readable data by the ML model that were not readable before.
2.  **Create a testing data set and a training data set**
    1.  **Training data set**: contains 80% of the original data set and is fed to our ML model in order to allow it to see what KPIs correlate to what grades so that when it gets a new venture it can determine the grades without ever even seeing the venture before.
    2.  **Testing data set**: contains 20% of the original data set however does not include any of the grades. This is so that the ML model can use what they gained from the training set analysis to now determine on its own the grade of each venture
3.  **Next we send all this to our ML model for it to digest and figure out the testing set**
    1.  SVM Classification Model: A classifier model that is able to determine complex relationships in datasets better than linear regression. It allows us use of multiple categories which gives us a letter grade scale to grade each venture's KPIs (A, B, C, D, F).
    2.  Accuracy: This section in our program just tells us how many predictions the model was able to guess correctly but expressed as a percentage.
4.  **Finally, we can go to the prediction stage**
    1.  In the prediction stage all the user needs to do is enter the KPIs, Venture name, and date of analysis in order to determine by the model the probability of the given venture succeeding.
    2.  Then the output will be your grade and that would wrap up the model.

## **Example Use Cases of the Venture Selection Model in Predicting Future Outcomes:**

1.  Sears Holdings: Sears used to be a direct competitor to huge retails stores such as Home Depot, Walmart, and Macy's which are still thriving today. However, unlike the mentioned competitors Sears is now struggling and the company has plans now to file for bankruptcy unfortunately. I found this interesting since not only was Sears a good rival to these retail stores but were always very smart with their social media influencing and advertising of the store. Which leads me to ponder the question can my machine learning model determine from the earliest KPIs available in 2009 that Sears in the future would prove to be a bad investment? Let's find out!

Downfall of Sears Article: <https://www.investopedia.com/news/downfall-of-sears/>

Where KPIs were acquired: <https://www.macrotrends.net/stocks/charts/SHLDQ/sears-holdings/roi>

Investment Name: Sears Holdings, Date of KPIs: 10/31/2009, ROI: -.04%, Debt To Equity Ratio: .22, Profit Margin: 27.43%, Social Media Engagement: 7 , PE Ratio: 0

![sears](https://github.com/AryaJ3365/Investment-Prediction-Application/assets/91634509/9545ce74-5d9c-4241-8026-34b0b963965d)


As we can see from the above screenshot, even though at the time these financials were taken no one would even think about not investing in Sears with such a safe debt to equity ratio and high profit margin it still received a grade of C. Thus, I believe this shows the strength of the machine learning model to have the capability to predict if a venture could potentially fail in the future.

1.  AMD: During the 2010 era AMD was seen as a direct competitor to Intel CPUs, however, most at the time saw Intel as much more valuable and would neglect AMD as even a competitor. Thus, when you look at AMD financials from 2010 nothing would scream of a company that is worth investing in. However, I decided to see if my ML model given AMD financials from 2010 could potentially predict that AMD may end up becoming a strong company that would definitely have been worth investing in.

    Talks about AMD's struggles in 2010: <https://www.latimes.com/business/la-xpm-2011-nov-25-la-fi-amd-20111125-story.html>

    Where KPIs were acquired: <https://www.macrotrends.net/stocks/charts/AMD/amd/gross-profit>

    Investment Name: AMD, Date of KPIs: 10/31/2009, ROI: 6.23%, Debt To Equity Ratio:-32.4, Profit Margin: 42.05%, Social Media Engagement: 5 , PE Ratio: 21.51

![AMD](https://github.com/AryaJ3365/Investment-Prediction-Application/assets/91634509/1fb2d7ec-f6d4-46ab-a36e-075dbd737d4c)


As we can see, even though at these financials were taken many would have seen AMD as just a struggling venture, we can see here that our ML model doesn't see it that way and would rather have us invest in the venture than ignore it. Almost makes me which I had this app earlier as I probably would have never had to work again if I went all in on AMD in 2010.

## **Explain the KPIs in the app and where all the KPI information came from:**

**Venture Information on:** Investment Name, Profit Margins, Return on Investment, Debt-to-Equity ratio, and P/E ratio all were collected from macrotrends.net

**Venture Information on Date column:** Comes from the date in the charts where I recorded the KPIs for each venture. Intentionally I tried to get the earliest data I could on each venture in order to feed more relevant data when comparing big ventures to startups. The earliest the data goes back for most ventures was 12/31/2009 so if that was the earliest option that is what I chose for most of the ventures.

**Venture Information on Successful Column:** This column is primarily subjective because this how we train the ML model to understand what we deem are good and bad businesses.

**Reasoning:** There's no universal rating based on how good or bad a business is so that's what we have to figure out ourselves. Thus, we create initial ratings to showcase what we believe the venture should be at, then the ML model determines based on scores we gave for each row of kpis (venture) what are the typical KPIs that align with each score. It should be noted that for determining successful scores that they weren't random numbers but educated decisions based off of metrics and articles found from credible sources to make our ML model predictions as accurate as possible.

**Venture Information on Social Media Engagement Rate Column:** This column is primarily subjective because there is no singular statistic that dictates social media engagement, and no database that tracks it for each company. Thus, we came up with the closest and most accurate score we could give the venture based on views, bounce rate, pagers per visit, visit duration, and even the number of followers. Most of these statistics were found to allow us to give an accurate score using websites like similarweb.com.
