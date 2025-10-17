🧭 Early Signal
Democratizing public health and accelerating grassroots outbreak response with AI
<!-- IMAGE: Logo -->
📘 Table of Contents
Project Motivation
Overview of Early Signal
Project
 3.1 LLM Chatbot — Personal Health Intake and Guidance
 3.2 Alert System — Detecting Emerging Outbreaks
 3.3 Dashboards — Seeing the Signal
 3.4 Toolkit — Integrating AI and Infrastructure
Market Fit and Potential
Future Works
Tools Used
About the Team
References & Acknowledgements
1️⃣ Project Motivation
When outbreaks strike, official data often lags behind lived experience.
Early Signal was designed to close that gap — turning community observations into real-time intelligence.
Imagine Leah, a mother in Chicago whose child wakes up with a rash and fever. She opens the Early Signal app, chats with an AI assistant that helps her record symptoms, and instantly sees whether similar cases are appearing nearby.
Or Aiden, an immunocompromised student who checks the app before heading to class to see if respiratory illnesses are rising on campus.
Both use Early Signal for the same purpose: to protect themselves and their community through faster, smarter information.
Why It Matters
Traditional surveillance systems are centralized and slow; Early Signal empowers individuals to participate directly in outbreak detection.
By pairing AI-guided triage with collective intelligence, the project explores a new model of crowdsourced epidemiology — one that could help identify patterns days or even weeks before official alerts.
2️⃣ Overview of Early Signal
Early Signal brings together three interconnected systems:
an LLM-powered chatbot that guides users through symptom reporting and advice,
an alert system that analyzes community-level data for emerging clusters, and
a dashboard suite that visualizes local trends and risks.
<!-- IMAGE: Overview Diagram -->
Together, these components form an end-to-end loop: users contribute health data → AI interprets and classifies it → spatial models detect anomalies → the community receives early warnings.
3️⃣ Project
3.1 LLM Chatbot — Personal Health Intake and Guidance
<!-- IMAGE: Chatbot Flow -->
At the center of Early Signal is a conversational agent built on LangGraph, a framework for structuring complex AI dialogues.
When a user opens the app, the chatbot:
Collects key symptoms and their onset time in natural language.
Generates a preliminary diagnosis with a confidence estimate.
Asks follow-up questions about exposure location (where the illness may have been caught) and current location (where the user is now).
Offers care recommendations and guidance on when to seek medical help.
Each interaction contributes an anonymized record — including symptoms, diagnosis, and geolocation — to a secure data store.
As more users participate, the system gains “collective wisdom”: when multiple nearby users report similar patterns, the model refines its diagnostic confidence and improves local accuracy.
This approach merges personalized AI care with community-level insight — bridging private experience and public health awareness.
3.2 Alert System — Detecting Emerging Outbreaks
<!-- IMAGE: Alert System Pipeline -->
Every report from the chatbot feeds a pair of analytical pipelines hosted in BigQuery:
Tract-Based Alerts
Aggregates reports by census tract (small neighborhood zones).
Tracks week-over-week changes in case counts to flag sudden spikes or unusual increases.
Best suited for respiratory or community-spread diseases.
Cluster-Based Alerts
Groups cases by shared exposure sites — for example, “a restaurant” or “music festival.”
Uses spatial clustering to identify when several people report similar symptoms from the same area within a few days.
Ideal for food-borne or water-borne outbreaks.
When thresholds are crossed, the system issues localized alerts that appear in the user’s app feed and map view.
This structure balances breadth (tract analysis) with precision (cluster detection), creating a layered early-warning network.
3.3 Dashboards — Seeing the Signal
<!-- IMAGE: Dashboards -->
The app’s dashboard transforms community data into clear, actionable visuals:
Heatmaps highlight current and historical illness concentrations.
Pie and trend charts show disease distribution by category.
Filters allow users to explore by radius, exposure type, or timeframe.
Dashboards are generated dynamically from BigQuery through Firebase Cloud Functions, ensuring real-time accuracy while keeping user data private and authenticated.
These interfaces translate raw analytics into intuitive public insight — allowing citizens to “see” the health of their surroundings.
3.4 Toolkit — Integrating AI and Infrastructure
<!-- IMAGE: Toolkit -->
Early Signal combines research-grade AI with accessible mobile technology:
Layer	Description
Front End	Built in Flutter (Dart) for iOS and Android — a single responsive app that handles chat, maps, and dashboards.
Backend & Cloud	Firebase Authentication manages logins; Cloud Functions bridge the app with BigQuery for secure data queries.
AI Orchestration	LLM agents (Gemini 2.5 Flash) are structured using LangGraph to follow a multi-stage diagnostic flow.
Data & Storage	BigQuery for report aggregation and alert logic; optional vector search (Pinecone / SentenceTransformers) for symptom similarity.
This stack demonstrates how consumer-grade devices and cloud AI can collaborate to deliver population-level intelligence at minimal infrastructure cost.
4️⃣ Market Fit and Potential
Public health reporting is often reactive. Early Signal shifts the paradigm to proactive detection.
Use cases
Universities and schools monitoring campus health trends.
Local health departments supplementing official surveillance.
NGOs or emergency teams deploying in disaster zones.
Communities tracking seasonal illnesses or post-event exposures.
Comparable initiatives such as HealthMap and Flu Near You proved the feasibility of participatory surveillance; Early Signal extends those ideas with real-time AI triage and spatial clustering, producing faster, finer insights.
As adoption grows, anonymized data could inform early-intervention strategies, guide testing resources, and ultimately reduce outbreak impact.
5️⃣ Future Works
Early Signal is an evolving platform. Next phases include:
Partnering with local and state health departments to share aggregated alerts.
Establishing feedback loops with clinics or testing centers to validate diagnoses.
Extending coverage beyond the U.S. with global boundary datasets.
Adding SMS-based reporting for low-connectivity regions.
Expanding the “collective wisdom” logic to continuously re-train diagnostic confidence models.
Each step moves the system closer to a living, decentralized network for public-health intelligence.
6️⃣ Tools Used
(Adapted from LIA’s format — edit rows to fit your final stack)
Category	Tools & Frameworks
Front-End Development	Flutter (Dart), Google Maps SDK, Firebase Authentication
Back-End Development	FastAPI, Firebase Cloud Functions, BigQuery
AI / NLP	Gemini 2.5 Flash, LangGraph Orchestrator, SentenceTransformers
Data Storage & Analytics	BigQuery, Pinecone Vector DB
Deployment	Google Cloud Platform (GCP), Firebase Hosting
Visualization	Flutter Charts, BigQuery Views, Custom Dashboards
7️⃣ About the Team
Name	Role	LinkedIn
Alex Rivera	AI Systems Architect	LinkedIn
Priya Mehta	Frontend Engineer	LinkedIn
Jordan Lee	Backend & Cloud Engineer	LinkedIn
Mahima Masetty	Project Lead & Data Scientist	LinkedIn
8️⃣ References & Acknowledgements
<!-- Add citations or project credits here -->
Examples:
HealthMap Project – Boston Children’s Hospital
Flu Near You (CDC & Harvard Pilgrim Institute)
BlueDot – AI Epidemic Intelligence
U.S. CDC Syndromic Surveillance Reports

