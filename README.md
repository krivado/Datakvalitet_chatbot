# Datakvalitet_chatbot

Detta projekt genomfördes inom kursen **Datakvalitet** på Data Management utbildningen vid TUC Yrkeshögskola.

Projektets mål var att bygga en RAG applikation (Retrieval Augmented Generation) med hjälp av Airbnb data och samtidigt undersöka hur datakvalitet påverkar svaren från en språkmodell.

I projektet användes en vektordatabas där den förbehandlade datan sparades och sedan användes som kontext till språkmodellen för att ge mer relevanta svar.

## Projektets innehåll

Projektet består av två huvuddelar:

**1. Datastädning och förbehandling**
* Undersökning av datakvalitet
* Hantering av saknade värden
* Kontroll av extrema värden
* Standardisering av textfält
* Förberedelse av data inför RAG systemet

**2. Airbnb RAG chatbot**
* Inläsning av CSV data
* Chunking och embedding
* Sparande i vektordatabas
* Retrieval
* Frågor till LLM med kontext från datan

## Dataset

Datasetet innehåller Airbnb listningar från flera städer och användes för att bygga chatboten.

Exempel på kolumner:

* host_id
* price
* room_type
* minimum_nights
* number_of_reviews
* licence

Datasetet innehåller cirka **290 000 boenden**.

Original data:

https://www.kaggle.com/datasets/darkmatternet/airbnb-listings-nyc-london-paris-tokyo-and-more?resource=download

Den ursprungliga datan kommer från **Inside Airbnb**, som samlar in offentligt tillgänglig information från Airbnb listningar.

## ETL process

Projektet följde en enkel ETL process:

**Extract**
Data hämtades från Kaggle.

**Transform**
Datan undersöktes och förbereddes genom arbete med datakvalitet, exempelvis:

* Completeness
* Uniqueness
* Validity
* Consistency
* Accuracy

**Load**
Den bearbetade datan sparades i vektordatabasen och användes i RAG systemet.

## Projektstruktur

```bash
Datakvalitet_chatbot/
│
├── data/
│   └── airbnb_cleaned.csv
│
├── airbnb_chatbot.ipynb
├── cleaning_data.ipynb
├── requirements.txt
└── README.md




--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------



Installation
Skapa virtuell miljö:
python -m venv .venv

Aktivera miljön:
Windows:
.venv\Scripts\activate

Installera paket:
pip install -r requirements.txt

Exempel på fråga till chatboten
Can you recommend Airbnb accommodations in Rome with their price range and many reviews?
->
RAG systemet använder då data från vektordatabasen som kontext för att ge mer relevanta svar.
