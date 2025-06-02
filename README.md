## Analyzing Customer Satisfaction from Yelp Reviews (2009-2022) in STAR Format

### Situation
In the competitive, market-oriented business landscape, understanding customer satisfaction is critical for companies to thrive. The rise of online platforms like Yelp has generated vast amounts of user-generated review data, offering valuable insights into customer needs and preferences. Businesses face the challenge of analyzing this unstructured text data to identify key drivers of satisfaction and adapt to evolving customer expectations. 

### Task
Provide actionable insights for businesses to enhance customer satisfaction, loyalty, and profitability. This project leverages Yelp reviews from 2009 to 2022 to explore customer satisfaction trends across 16 U.S. states. Download the data from this link https://business.yelp.com/data/resources/open-dataset/ and choose the 4.35GB TAR file. 

The primary objectives of this project were twofold:

i) To demonstrate the importance of quantitative text mining methods in decision-making and creating competitive advantages for businesses.
ii) To identify the drivers of customer satisfaction by analyzing Yelp reviews, answering four-- research questions:
- What are the most frequently occurring words in Yelp customer reviews?
- What are the most frequently occurring phrases in Yelp customer reviews?
- Are there differences in Yelp reviews based on the state where the business is located?

How frequently do words from Giese and Cote’s conceptual model of customer satisfaction appear in Yelp reviews?

### Action
To address the research questions, the following actions were taken using the Cross-Industry Standard Process for Data Mining (CRISP-DM) methodology. 

<img width="391" alt="Screenshot 2025-06-02 at 2 36 13 AM" src="https://github.com/user-attachments/assets/c9c78813-4466-4741-9401-2f12874b43b4" />

**Data Understanding:** Collected two JSON files (118.9 MB and 180.6 MB) from Yelp’s dataset, containing business details and customer reviews. These were merged using business identification keys, resulting in a dataset of 908,910 rows with 7 variables (business name, address, city, review text, state, postal code, and date). Due to processing constraints, a 10% random subset was used for this project.

**Data Preparation:**
The textual data (reviews) were preprocessed using **python (with RStudio) and packages like tidyverse, tidytext, and tm.**

Built a **corpus** (a corpus is a collection of text documents, like gathering all Yelp reviews into one big set for analysis), **converted the corpus to lowercase** (made all letters lowercase so "Great" and "great" count as the same word), **removed punctuation** (like commas, periods, and exclamation points), **removed whitespace in the reviews** (extra spaces or blank lines), and **removed stop words** (common words like "the," "and," "is" that don’t add much meaning), and **applied stemming/lemmatization** (simplified words, e.g., stemming turns "running" to "run," lemmatization turns "better" to "good"; this is important to group similar words and reduce the number of unique words to analyze) to reduce data size (makes the data smaller and easier to process).

**Created a document term matrix for analysis** (A spreadsheet where rows are reviews, columns are words, and cells show how often each word appears; it’s important because it lets us count and compare words like "food" or "service" across reviews to find what customers care about most).

**Modeling:**
**Research Q1 (Frequent Words):** Used term frequency (TF) and term frequency-inverse document frequency (TF-IDF) to identify high-frequency words.

**Research Q2 (Frequent Phrases):** Tokenized reviews into bigrams, removed stop words, and analyzed phrase frequency using TF-IDF.

**Research Q3 (State-Based Differences):** Employed the **tidyverse package’s group_by()** function to compare high-frequency words across states.

**Research Q4 (Giese and Cote Model):** Constructed a dictionary with words from Giese and Cote’s model (“quality,” “value,” “expect,” “complain,” “loyalty,” “service,” “satisfy”) and analyzed their frequency in reviews using TF and TF-IDF.

**Evaluation:** Visualized results using ggplot2, producing figures to illustrate word/phrase frequencies and state-based differences.

**Deployment:** Summarized findings and provided recommendations for businesses to improve service quality, food quality, and customer experience.


### Result
The analysis yielded the following key findings:

**Research Q1 (Frequent Words):** The top 10 high-frequency words across Yelp reviews were “food,” “service,” “love,” “amazing,” “delicious,” “awesome,” “time,” “friendly,” “nice,” and “staff,” indicating a focus on food quality and service experience.

**Research Q2 (Frequent Phrases):** Top bigrams included “mountain dining,” “you’d expect,” “hair cut,” “awesome atmosphere,” and “fresh food,” with notable prevalence in states like Connecticut, South Dakota, and New Jersey.

**Research Q3 (State-Based Differences):** While common words like “food” and “service” appeared across all states, some states showed unique preferences (e.g., “atmosphere” and “sculpted” in South Dakota, “tucson” in Arizona). 

**Research Q4 (Giese and Cote Model):** Words from the model were prevalent in reviews, with “service” appearing in 85% of reviews, “quality” in 8.5%, “expect” in 3.7%, “value” in 1.7%, “satisfied” in 0.5%, and “loyalty” and “complain” in 0.4% each, confirming the model’s relevance.

**Business Impact:**
- The findings underscored the universal importance of service and food quality, consistent with Giese and Cote’s model and expectancy disconfirmation theory.

- Recommendations included prioritizing prompt service, friendly staff, high food quality, and a conducive atmosphere. Businesses were advised to leverage marketing focused on service quality, offer personalized experiences, and incentivize reviews with rewards like gift cards.

- The study highlighted text mining’s role in extracting actionable insights, giving businesses a competitive edge in understanding customer needs.

**Limitations:**
- Uneven review distribution across states limited generalizability.
- Lack of keyword context analysis may obscure nuanced meanings.

**Future Research:**
- Conduct context analysis of keywords/phrases.
- Ensure balanced representation of businesses across states.
- Expand analysis to include the remaining 34 U.S. states.
- This project successfully demonstrated the power of text mining in uncovering customer satisfaction drivers, providing businesses with data-driven strategies to enhance customer experiences and profitability.
