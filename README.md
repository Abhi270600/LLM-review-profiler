# AI Engineering Challenge: Extracting Property Profiles from Airbnb Reviews

## Context

You are an AI engineer supporting an Airbnb portfolio manager with properties across Paris. The team has heard mixed signals from guests — some neighborhoods are getting rave reviews, others are seeing complaints, and it's unclear why certain properties resonate with guests. Your job is to make sense of the data by surfacing the guest experience signals hidden in the review text.

---

## Dataset

Use the **Inside Airbnb** dataset for Paris: [insideairbnb.com/get-the-data](http://insideairbnb.com/get-the-data)

Download the most recent Paris snapshot. The file you'll need is:
- `reviews.csv` — guest review text

You are invited to explore other files in the snapshot if you find them useful. These others will give you additional context about the market.

---

## What to Implement

Using a sample* of Airbnb reviews, build and evaluate a pipeline that uses a **reasoning LLM** to extract **structured property profile summaries** for each listing from raw reviews — a concise, factual synthesis of what reviewers collectively say about the property. You decide what fields to extract, how to prompt for them, how to parse and validate the output, and how to measure reliability. 


### Component 1 - Text preparation pipeline for reasoning LLM

Build a pipeline that prepares raw Airbnb reviews for input into a reasoning model. The quality of what a model produces is tightly coupled to the quality of what it receives — and with reasoning-capable models, that relationship also has direct cost implications that compound quickly at volume. Consider what the model actually needs, what adds noise, and what drives token cost without adding signal.

### Component 2 — Extracting structured information from Airbnb reviews 

Build a pipeline that submits the prepared reviews for a property listing to a reasoning LLM and returns structured output. Getting reliable structured output from an LLM at scale requires more than a working prompt; it requires understanding where and why the model fails. Document your prompt design and how your parsing logic handles imperfect LLM responses.

### Component 3 - Reliability and cost analyses

Answer the following questions, and support your answers with your choice of visualizations:
- What does the review corpus look like before and after your data preparation pipeline, and what did your preparation choices actually change?
- How consistent and accurate is your structured profile extraction? Where does it break down, and why?
- If the full pipeline were used to process 10,000 property listings at scale, what are the accuracy, cost, and operational considerations? What human review process would you recommend, and at what volume?
