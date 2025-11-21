## 📄 REWRITTEN README.md (Gemini TruthLens)

````markdown
# 🌟 Gemini TruthLens: Explainable Multimodal Deepfake Detector

Gemini TruthLens is a cutting-edge forensic intelligence tool designed to detect deepfake images and videos. Unlike traditional black-box classifiers, it uses **Gemini 1.5 Pro** for sophisticated, multimodal reasoning to provide **explainable authenticity reports** based on technical evidence from Google Cloud Vision and Video Intelligence APIs.

This project was built for the **[Insert Marathon/Challenge Name Here]** to demonstrate state-of-the-art integrity verification.

## ✨ Core Innovation: Explainable AI

The primary value is the fusion of forensic data:

1.  **Feature Extraction:** Google Cloud Vision/Video Intelligence APIs extract low-level artifacts (anatomical asymmetry, temporal inconsistencies, compression flags).
2.  **Multimodal Reasoning:** **Gemini 1.5 Pro** synthesizes this raw data, assesses the correlation between artifacts, and generates a plain-language **Forensic Evidence Coherence Score (FECS)** and a final confidence rating.

---

## 🚀 Features

* **🧠 Gemini 1.5 Pro Reasoning:** Provides detailed, human-readable explanations of *why* content is flagged, increasing user trust (high FECS).
* **🖼️ Multimodal Analysis:** Fuses data from **Google Cloud Vision API** (images) and **Google Video Intelligence API** (videos) for higher accuracy than single-model solutions.
* **📈 Weighted Scoring:** Uses a custom weighted algorithm to prioritize highly reliable forensic indicators (e.g., temporal artifacts over metadata flags).
* **🖥️ UI / Evidence Highlighting:** (Future/WIP) Web interface to display reports and visually highlight suspicious regions directly on the image/video frame using HTML5 Canvas.

---

## 🛠️ Technology Stack

| Component | Technology | Purpose |
| :--- | :--- | :--- |
| **Reasoning Engine** | **Gemini 1.5 Pro** | Synthesizes all forensic artifacts and generates the final explainable report. |
| **Image Analysis** | **Google Cloud Vision API** | Extracts bounding box coordinates, landmark asymmetry, and lighting properties. |
| **Video Analysis** | **Google Video Intelligence API** | Detects frame manipulation, temporal inconsistencies, and shot changes. |
| **Backend/Orchestration** | **Python (Cloud Run)** | Manages the full orchestration pipeline from GCS upload to API calls. |
| **Frontend/Demo** | **React / HTML5 Canvas** | User interface, file upload, and rendering of visual highlights. |

---

## ⚙️ Installation & Setup

This project is designed to run within the Google Cloud ecosystem.

### Prerequisites

* Python 3.9+
* A Google Cloud Project with Billing Enabled.
* APIs Enabled: **Gemini API, Cloud Vision API, Cloud Video Intelligence API.**
* Authentication: Set up Google Cloud Application Default Credentials (ADC).

### Step 1: Clone the Repository

```bash
# Clone the repository
git clone [https://github.com/your-username/Gemini-TruthLens.git](https://github.com/your-username/Gemini-TruthLens.git)

# Navigate to the project directory
cd Gemini-TruthLens
````

### Step 2: Install Dependencies

```bash
# Install required Python packages
pip install -r requirements.txt

# (Optional) Install the Google GenAI SDK for local testing
pip install google-genai
```

### Step 3: Run the Local Demo (Backend Service)

You can run the core processing service locally using the following command.

```bash
# Set your Gemini API Key as an environment variable
export GEMINI_API_KEY="YOUR_API_KEY"

# Run the core analysis service
python run_analysis.py --file path/to/sample_media.mp4
```

### Example Output (Snippet)

The script returns a JSON report containing the raw data and Gemini's analysis:

```json
{
  "confidence_score": 87.5,
  "is_fake": true,
  "gemini_report": "The content is highly likely synthetic (87.5%). The Cloud Vision API detected significant asymmetry in the facial landmarks (L/R eye angle discrepancy of 4.2°), which contradicts the highly stable temporal stream reported by the Video API. This suggests a post-production deepfake insertion onto a clean background plate. Focus verification on coordinates [X,Y]."
}
```

-----

## 👥 Creators & Maintainers

This project is created and maintained by **Anirudh and Prakash**.

-----

## 🤝 Contributing

Contributions are welcome\! Please fork the repository and submit a pull request with your improvements. We are currently looking for contributions in:

  * Cross-browser testing for the Canvas highlighting feature.
  * Advanced prompt engineering for the Gemini Causal Reasoning step.
