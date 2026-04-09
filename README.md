# Welcome to Food Decoder!

**Food Decoder** is an **open source**, lightweight full stack web application designed to help people know what they are consuming on daily basis.
**Helps maintain dieting**, **body building plans** and **helps in maintaining a healthy lifestyle** using AI models and Ingredients(fetched from world.openfoodfacts.org) in the packaged food.


# Features

-   **Live Barcode Scanning:** Native in-browser scanning using device cameras (no app download required).
    
-   **Vision AI Fallback:** Upload a photo of a food label if the barcode isn't recognized, utilizing Vision LLMs to extract ingredient text automatically. **(This uses Nvidia nemotron nano 12b v2 vl)**
    
-   **AI Health Analysis:**  Automatically generates a **Health Score** , **highlights positive nutritional traits**, and flags potential concerns (like hidden sugars, artificial additives, emulsifiers, food dyes etc.).
    
-   **User Friendly UI:** A premium, responsive frontend featuring glassmorphism, 3D interactive cards, magnetic buttons, and smooth momentum scrolling.
    
-   **Resilient Backend:** A FastAPI backend hosted on Hugging Face that seamlessly routes traffic between Gemini 2.5 Flash and an OpenRouter fallback (Nemotron) to ensure 100% uptime.

## Tech Stack

**Frontend**

-   HTML5, CSS3, Vanilla JavaScript
    
-   [HTML5-QRCode](https://github.com/mebjas/html5-qrcode) (For client-side barcode scanning)
    
-   Custom CSS animations & 3D tilt effects(3d effects are only visible in desktop version)
    

**Backend & AI**

-   **Python Framework:** Fastapi
    
-   **Hosting:** Hugging Face Spaces
    
-   **Primary LLM:** Google Gemini 2.5 Flash
    
-   **Fallback LLM:** Nvidia Nemotron-12b (via OpenRouter)
    
-   **Food Database:** [Open Food Facts API](https://world.openfoodfacts.org/data)

## How does it work??

## How It Works

1.  **Scan or Upload:** If the database contains the product scanning the barcode(usually behind the food package) can give instant insights but if you want deeper analysis or the product is not in the database you can take a photo of the backside of the product which will give a more detailed insight.
    
2.  **Database Lookup:** If a barcode is scanned, the app pings the Open Food Facts API to retrieve the raw ingredient string.
    
3.  **AI Processing:** The text (or image) is sent securely to the FastAPI backend. A highly specific prompt forces the LLM to act as a toxicologist/nutritionist, returning a strictly formatted JSON object.
    
4.  **Interactive Report:** The frontend parses the JSON and renders a beautiful, color-coded report card detailing the food's safety profile.

## Local Installation

Idk why would anyone install it locally but here are the steps to do so:-

1. **Clone the Repo** 
  -

     git clone https://github.com/adityaprasad-sudo/FoodAnalayser.git
        cd FoodAnalayser

2. Setup the api keys
- make .env file in the cloned repo
-

    this goes into your .env file and put your gemini api key in the chiggaapi and openrouter api key in the opapikey
    chiggaapi=YOUR_GEMINI_API_KEY
    opapikey=YOUR_OPENROUTER_API_KEY

3.Install dependencies

        pip install fastapi uvicorn google-generativeai pillow requests python-dotenv python-multipart
    uvicorn main:app --reload --port 7860
4.Runing the frontend

- You can serve the HTML/CSS/JS files using any standard live server (like the VS Code Live Server extension)

Note: Camera access in browsers requires either a `localhost` or `https://` connection


# Disclaimer

_DecodeFood is built for educational and informational purposes only. The AI-generated health scores and insights do not constitute professional medical advice. Users with severe food allergies should always verify ingredients on the physical packaging._

## Author

Built with ❤️ by **Aditya Prasad** * GitHub: [@adityaprasad-sudo](https://github.com/adityaprasad-sudo)



## Flowchart

![flowchart](https://i.ibb.co/k2CP7xGg/Product-Purchase-Decision-2026-04-06-145301.png)

## Screenshots and Demo
item used in the video - [Amazon](https://www.amazon.in/Kissan-Mixed-Fruit-Jam-700g/dp/B00N2WRE52/ref=sr_1_6?sr=8-6)

- Demo Video

(https://drive.google.com/file/d/1url-S7SR59TI-1AMfo4ylVShVGI_h3xj/view?usp=sharing)

- Demo Screenshots

<img width="484" height="1023" alt="Screenshot 2026-04-09 173820" src="https://github.com/user-attachments/assets/def03436-af1e-448d-9e10-8188df2b74d6" />
<img width="483" height="1023" alt="Screenshot 2026-04-09 173918" src="https://github.com/user-attachments/assets/150becff-ffd8-4d80-90c6-8eaf5dd8f8af" />


## Which Barcode to Scan?
<img width="683" height="696" alt="Screenshot 2026-04-09 174020" src="https://github.com/user-attachments/assets/a9fabb9c-4cef-4848-a16d-b60af2acc042" />

    
