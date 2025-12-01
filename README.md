# Astrolog Astrophotography Field Catalog Agent
The AstroLog Agent is a sequential multi-agent system that autonomously researches, compiles, and formats all necessary meteorological, scientific, and processing data into a professional PDF log artifact for your astrophotography imaging session.

________________________________________
Quick Start in Google Colab

The easiest way to run this project is directly in your Google Colab account.

Prerequisites

1.	Google Account: You must be signed into a Google account.
2.	API Key: A valid Gemini API Key is required to power the agents.

Step 1: Open the Notebook

1.	Open the main project file: Astrophotography_Field_Catalog_Agent.ipynb
2.	(Optional) Save a copy to your Google Drive.

 
Step 2: Setup and Configuration

In the Colab notebook, follow the cells sequentially:
1.	Run Cell 1: Install Dependencies
○	Execute the first code cell to install the necessary libraries (google-adk, fpdf, pillow).
2.	Run Cell 2: Configure API Key
○	Enter your Gemini API Key when prompted. The notebook securely configures the environment.

Step 3: Running the Agent

The final cells handle file upload and agent execution.
1.	Upload Sample Image
○	Execute the file upload cell.
○	Upload a sample image (e.g., from the sample_images folder) or use your own image.
2.	Set Agent Parameters
○	In the final execution cell, ensure the target_name (e.g., "Whirlpool Galaxy (M51)") and image_filename variables match your input.
3.	Execute the Agent Pipeline
○	Run the final code cell. The multi-agent pipeline will execute the sequential flow (Location, Research, Record) and generate the report.
Step 4: Check Output

A new file named AstroLog_[Target Name].pdf (e.g., AstroLog_Whirlpool_Galaxy.pdf) will be generated and available for download in your Colab file browser. See sample output in the sample_astrolog directory for reference.
________________________________________
 
Architecture & Implementation

The solution is built on a robust multi-agent architecture, demonstrating several key concepts from the ADK:

Agent Architecture: Sequential Pipeline

The system uses a Sequential Multi-Agent System where agents execute in a strict, ordered flow, passing data via shared state management.
Stage	Agent Name	Function
1. 🌍	LocationAgent	Retrieves geo-location and weather data using Google Search.
2. 🔬	ResearchAgent	Retrieves scientific facts about the target using Google Search.
3. 📝	AstroRecordAgent	Compiles all data and calls the Custom Tool for PDF creation.
Process: User Input -> LocationAgent -> ResearchAgent -> AstroRecordAgent -> Final Catalog PDF

 
Key Concepts Demonstrated

●	Sequential Agents: Orchestrates the multi-step log creation process.
●	Custom Tools: Integrates the process_astro_log function for image processing and final PDF generation.
●	Built-in Tools: Uses Google Search extensively for data retrieval (weather, astronomical facts).
●	State Management: Passes compiled data reliably between agents in the pipeline.
●	Effective Use of Gemini: All sub-agents are powered by Gemini 2.5 Flash Lite for intelligent tool-use and instruction execution.
