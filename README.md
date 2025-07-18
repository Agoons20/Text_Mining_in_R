## Analyzing Customer Satisfaction from Yelp Reviews (2005-2022)

### Situation
In the competitive, market-oriented business landscape, understanding customer satisfaction is critical for companies to thrive. The rise of online platforms like Yelp has generated vast amounts of user-generated review data, offering valuable insights into customer needs and preferences. Businesses face the challenge of analyzing this unstructured text data to identify key drivers of satisfaction and adapt to evolving customer expectations. 

### Task
Provide actionable insights for businesses to enhance customer satisfaction, loyalty, and profitability using Yelp reviews from 2005 to 2022 across 19 U.S. states. Download the data from this link https://business.yelp.com/data/resources/open-dataset/ and choose the 4.35GB TAR file. 

I set out to answer the following questions: 
- What are the most frequently occurring words in Yelp customer reviews across states and across the different business categories?
- Are there differences in Yelp reviews based on the state where the business is located?
- Demonstrate how to investigate reviews for a particular phrase or particular keyword using a 'dictionary'.

### Action
To address the research questions, the following actions were taken using the Cross-Industry Standard Process for Data Mining (CRISP-DM) methodology. 

<img width="391" alt="Screenshot 2025-06-02 at 2 36 13 AM" src="https://github.com/user-attachments/assets/c9c78813-4466-4741-9401-2f12874b43b4" />

**Data Understanding:** Collected two JSON files (118.9 MB and 180.6 MB) from Yelp’s dataset, containing business details and customer reviews. These were merged using business identification keys, resulting in a dataset of 6,990,280 rows with 22 variables. Due to processing constraints, a 1.45% stratefied sample was used for this project due to processing constraints.

**Data Preparation:**
- Built a **corpus** (a corpus is a collection of text documents, like gathering all Yelp reviews into one big set for analysis)
- **converted the corpus to lowercase** (made all letters lowercase so "Great" and "great" count as the same word) 
- **removed punctuation** (like commas, periods, and exclamation points), **removed whitespace in the reviews** (extra spaces or blank lines)
- **removed stop words** (common words like "the," "and," "is" that don’t add much meaning), and 
- **applied stemming/lemmatization** (simplified words, e.g., stemming turns "running" to "run" lemmatization turns "better" to "good"; this is important to group similar words and reduce the number of unique words to analyze) to reduce data size (makes the data smaller and easier to process).

- **Tokenize the corpus** (A spreadsheet where rows are reviews, columns are words, and cells show how often each word appears; it’s important because it lets us count and compare words like "food" or "service" across reviews to find what customers care about most).

**Analysis**
- **Frequent Words:** Used term frequency (TF) and term frequency-inverse document frequency (TF-IDF) to identify high-frequency words. 

- **Frequent Phrases:** Tokenized reviews into bigrams, trigrams removed stop words, and analyzed phrase frequency using TF-IDF across states and business categories to see what customers think across states and across business categories.

- **Inspect the corpus for particular words:** Constructed a dictionary with words from Giese and Cote’s customer satisfaction model (“quality,” “value,” “expect,” “complain,” “loyalty,” “service,” “satisfy”) and analyzed their frequency in reviews using term frequency (TF) and term frequency-inverse document frequency (TF-IDF).


### Result
The analysis yielded the following key findings:

**Frequent Words:** The top 10 high-frequency words across Yelp reviews were “food,” “service,” “love,” “amazing,” “delicious,” “awesome,” “time,” “friendly,” “nice,” and “staff,” indicating a focus on food quality and service experience.

**Frequent Phrases:** Top bigrams included “mountain dining,”, “awesome atmosphere,” and “fresh food”, "great service quality", "staff super friendly" with notable prevalence in states like Connecticut, South Dakota, and New Jersey.

**State-Based Differences:** While common words like “food” and “service” appeared across all states, some states showed unique preferences across various business categories.

**Giese and Cote Model:** Words from the model were prevalent in reviews, with “service” appearing in 85% of reviews, “quality” in 8.5%, “expect” in 3.7%, “value” in 1.7%, “satisfied” in 0.5%, and “loyalty” and “complain” in 0.4% each, confirming the model’s relevance.

**Business Impact:**
- The findings underscored the universal importance of service and food quality, consistent with Giese and Cote’s model and expectancy disconfirmation theory.

- Recommendations included prioritizing prompt service, friendly staff, high food quality, quick service and a conducive atmosphere. Businesses are advised to leverage marketing focused on service quality, offer personalized experiences, and incentivize reviews with rewards like gift cards.

- The study highlighted text mining’s role in extracting actionable insights, giving businesses a competitive edge in understanding customer needs.

**Limitations:**
- Uneven review distribution across states limited generalizability.
- Lack of keyword context analysis may obscure nuanced meanings.
