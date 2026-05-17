# Touch-of-Nature
My helpful code for ESG metric report generation using API integration (secure)
A premium enterprise-grade single-file frontend web application for AI-driven environmental analysis, botanical recommendation, and sustainability reporting.


🎯 Project Overview
EcoSuggest is a fully self-contained ESG (Environmental, Social, and Governance) Decision Dashboard built for environmental analysts. It accepts complex multi-dimensional environmental data, runs intelligent analysis via multiple backend modes, and delivers professional botanical and infrastructural ESG proposals with interactive visualizations and PDF export.

🗂️ Project Structure
eco-suggest-dashboard/
├── index.html                          ← Complete single-file frontend application
├── .gitignore                          ← Prevents secrets from being committed
├── README.md                           ← This file
└── supabase/
    ├── config.toml                     ← Supabase CLI configuration
    └── functions/
        └── generate-esg/
            └── index.ts               ← TypeScript Supabase Edge Function

✨ Key Features
🔌 Three Connectivity Modes
ModeDescriptionAPI Key RequiredLocal SimulationBuilt-in intelligent JS engine with ecosystem-specific proposals❌ NoneOpenRouter (Direct)Calls OpenRouter API directly from browser✅ OpenRouter keySupabase Edge FunctionSecure production mode — LLM keys stay server-side✅ Supabase Anon key
📊 14 Environmental Input Sliders
Real-time severity color-coding (Green/Yellow/Red) updates dynamically as you adjust:

Soil pH, Annual Rainfall, Temperature, AQI, Humidity, Groundwater Level
Wind Speed, Green Cover %, Biodiversity Score, Water Quality Index
Noise Pollution, Carbon Emission Density, Waste Management %, Renewable Energy %

🌍 Geographic & Climate Context

Climate Zone selector, Elevation, Distance from Water Bodies
Population Density, Urbanization Rate

⚠️ Risk & Sustainability Metrics

Flood Probability, Heatwave Frequency, Wildfire Risk
Drought Severity Index, Soil Fertility Score, Climate Resilience Score

🚀 Quick Presets
Instantly auto-populate all 25+ sliders for 5 ecosystem archetypes:

🏜️ Arid/Desertified Zone
🏙️ Urban Concrete Jungle
🏭 Industrial Hotspot
🌊 Coastal Wetland
🌿 Tropical Forest

📡 Live ESG Score
Formula-based real-time scoring (0-100) visible in header, updating as sliders move.
🔮 Predictive Scenario Simulator
Test macro-shift scenarios before running the full analysis:

"What if AQI worsens by 25% in 5 years?"
"Impact of adding +20% green cover?"

📋 AI-Generated ESG Report Dashboard

Executive Summary Card — ecosystem health overview
Animated SVG Gauges — Current ESG, Resilience, Vulnerability, Projected ESG
Environmental Risk Heatmap — 10×10 localized risk grid
Radar Chart (Chart.js) — Current vs Projected across 7 dimensions
Botanical Proposals — 5-6 scientifically appropriate native tree species with CO₂ data
Infrastructure Solutions — 5-6 domain-specific interventions (Water/Carbon/Cooling/Energy/Biodiversity)
Before/After Transformation — side-by-side sustainability comparison

📄 PDF Export
One-click professional corporate PDF report via html2pdf.js.

🚀 Getting Started
Option A: Local Simulation (Instant, No Setup)

Open index.html directly in any modern browser
Click "Generate ESG Proposal"
Adjust sliders, apply presets, explore the output

Option B: OpenRouter API

Get a free API key at openrouter.ai
Click the ⚙️ Settings gear icon in the header
Select "OpenRouter" tab
Enter your API key and model string (e.g. anthropic/claude-3-haiku)
Click "Save & Connect"

Option C: Supabase Edge Function (Production)
1. Deploy the Edge Function
bash# Install Supabase CLI
npm install -g supabase

# Login
supabase login

# Link to your project
supabase link --project-ref YOUR_PROJECT_REF

# Set your OpenRouter key as a secret (NEVER commit this)
supabase secrets set OPENROUTER_API_KEY=sk-or-v1-your-key-here
supabase secrets set OPENROUTER_MODEL=anthropic/claude-3-haiku

# Deploy the function
supabase functions deploy generate-esg
2. Configure the Frontend

Click ⚙️ Settings → "Supabase" tab
Enter your Edge Function URL:
https://YOUR_PROJECT_REF.supabase.co/functions/v1/generate-esg
Enter your Supabase Anon Key (safe to expose — it's public by design)
Click "Save & Connect"


🔒 Security Notes

Local Sim mode: No credentials required or stored
OpenRouter mode: API key stored in localStorage — suitable for personal use only
Supabase mode: OpenRouter API key lives in Supabase Vault secrets — never exposed to the browser. Only the public Supabase Anon Key is stored client-side, which is designed to be public


🧠 Local Simulation Engine
When no API is connected, the built-in simulation engine detects the ecosystem type from input parameters and returns hyper-realistic, ecologically accurate proposals:
EcosystemDetected WhenArid/DesertifiedRainfall < 300mm AND Temp > 30°CIndustrial-UrbanAQI > 200 OR Carbon Emission > 300 t/km²Dense UrbanUrbanization Rate > 70%TropicalRainfall > 2000mmCoastal WetlandFlood Prob > 40% AND Humidity > 70%TemperateDefault fallback
Each ecosystem archetype has hand-crafted, scientifically accurate tree species and infrastructure solutions.

📦 Tech Stack
LibraryVersionPurposeTailwind CSSCDNUtility-first stylingChart.js4.4.0Radar chart visualizationhtml2pdf.js0.10.1PDF exportLucide IconsLatestUI iconographyGoogle Fonts (Syne + DM Sans)—TypographyDeno / Supabase Edge Runtime—Backend function

🏆 ESG Report Schema
The AI returns (or the local engine generates) a structured JSON object:
json{
  "summary": "Executive summary string",
  "tree_recommendations": [
    {
      "species": "Quercus robur (English Oak)",
      "reason": "Ecological justification...",
      "co2_absorbed_per_year_kg": 48
    }
  ],
  "infrastructure_solutions": [
    {
      "type": "Water|Carbon|Cooling|Energy|Biodiversity",
      "solution": "Detailed solution description..."
    }
  ],
  "vulnerability_score": 65,
  "projected_improvement_score": 82
}

📝 License
MIT License — Built for the ESG hackathon.

EcoSuggest ESG Dashboard · Environmental Intelligence Platform · v2.0 Analyst Edition
