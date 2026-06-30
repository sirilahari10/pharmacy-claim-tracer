# Unpacking the 3%: Pharmacy Claims Pipeline & Trace Generator
*A Proof of Work for the Data Scientist II (Pharmacy) role at Oscar Health.*

## The Concept
Understanding where 3% of GDP goes requires tracing individual pharmacy claims to find systemic inefficiencies. This lightweight pipeline simulates ingesting messy pharmacy claims, flags cost anomalies (e.g., dispensing an expensive Brand name drug when a cheaper Generic is available), and outputs the results.

## The "Oscar" Architecture 
Inspired by Oscar's engineering blog posts on claims infrastructure and LLM Claim Assistants, this pipeline doesn't just output a flagged table. It generates a structured, stateless **Claim Trace (JSON)** for every claim. 

If a claim is flagged for high costs, the trace explicitly logs the execution path (Ingestion -> Formulary Check -> Affordability Check) so that data scientists (or LLMs) can immediately understand *why* the claim was flagged without reverse-engineering the pipeline.

## Run the Pipeline
`python pipeline.py`
