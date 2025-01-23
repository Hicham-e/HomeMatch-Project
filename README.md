HomeMatch Project Documentation

Project Overview
"HomeMatch" is a personalized real estate application that leverages Large Language Models (LLMs) and a vector database to provide tailored real estate listing recommendations based on buyer preferences. The application transforms real estate data into personalized property descriptions that resonate with individual needs.

Functionality
The "HomeMatch" application performs the following:
1. Generate Real Estate Listings: Uses an LLM to create synthetic real estate listings with information such as price, location, description, and amenities.
2. Store Listings in a Vector Database: Converts the generated listings into embeddings using OpenAIEmbeddings and stores them in a vector database (ChromaDB).
3. Semantic Search: Performs a semantic search to match buyer preferences with stored listings, retrieving the best-matching properties.
4. Personalized Listing Descriptions: Uses an LLM to rewrite property descriptions for the matched listings, emphasizing aspects that align with buyer preferences while retaining factual integrity.

How to Run the Code
1. Prerequisites
- Python Environment: Python 3.8 or above installed.
- API Key: API key for OpenAI to access the LLM and embeddings.

2. Install Dependencies
Install the required Python libraries using the following command:

pip install langchain openai chromadb


3. Run the Application
- Generate Listings:
   The application generates at least 10 synthetic real estate listings using an LLM. The listings include details like price, location, and descriptions.
   
- Store Listings in a Vector Database:
   The generated listings are embedded using OpenAIEmbeddings and stored in ChromaDB for semantic search.

- Enter Buyer Preferences:
   Provide buyer preferences (e.g., location, price range, desired amenities). This can be done by modifying the preferences dictionary in the code.

- Retrieve Best-Matching Listings:
   The application performs a semantic search, retrieving listings that match the buyer's preferences.

- Generate Personalized Descriptions:
   The LLM rewrites the descriptions of the matched listings, emphasizing the buyer’s specific needs.

Run the Jupyter Notebook (HomeMatch.ipynb) to execute the steps above.

Project Workflow
1. Generating Listings
- The LLM generates property listings with structured details. Example:
  Listing 1:
  Neighborhood: Green Oaks
  Price: $750,000
  Description: A cozy 3-bedroom home with energy-efficient features and natural lighting.

2. Storing Listings in ChromaDB
- Each listing is converted into a vector embedding and stored in ChromaDB for fast semantic search.

3. Performing Semantic Search
- Buyer preferences (e.g., desired location, price range, lifestyle) are converted into a query.
- The semantic search retrieves listings that match these preferences based on vector similarity.

4. Personalizing Listings
- Matching listings are passed to the LLM, which rewrites the descriptions to highlight the buyer’s preferences. For example:
  - Original: "A cozy 3-bedroom home with energy-efficient features."
  - Personalized: "This eco-friendly 3-bedroom home in Green Oaks offers energy-efficient features and a peaceful ambiance, perfect for a nature-loving family."

Example Output
Buyer Preferences:
preferences = {
    'location': 'Green Oaks',
    'price_range': '$700,000 - $850,000',
    'bedrooms': 3,
    'bathrooms': 2,
    'amenities': ['energy-efficient kitchen', 'large backyard', 'bike-friendly paths'],
    'lifestyle': 'eco-friendly, close to parks, and community-oriented'
}

Enhanced Listings:
Listing 1:
Embrace eco-friendly living in this charming 3-bedroom, 2-bathroom home located in Green Oaks. The spacious living room is perfect for relaxing, and the energy-efficient kitchen features modern appliances ideal for environmentally-conscious buyers. Priced at $750,000.

Listing 2:
If you're looking for a family-friendly home that offers both space and sustainability, this 4-bedroom, 3-bathroom beauty in Green Oaks is for you. The large backyard is perfect for gardening, while the modern kitchen caters to the eco-conscious. Priced at $820,000.

Code Structure
- HomeMatch.ipynb: Contains the complete implementation of the application.
- listings.txt: Stores the LLM-generated real estate listings.
- HomeMatchReadme.txt: Project documentation file (this file).

Dependencies
The project depends on the following Python packages:
- langchain: To interact with the LLM and embeddings.
- openai: For generating listings and embeddings.
- chromadb: For creating and querying the vector database.

Install all dependencies using the provided pip install command.
