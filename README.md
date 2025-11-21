# 🌟 Gemini TruthLens: Explainable Multimodal Deepfake Detector

Gemini TruthLens is a cutting-edge forensic intelligence tool designed to detect deepfake images and videos. Unlike traditional black-box classifiers, it uses **Gemini 1.5 Pro** for sophisticated, multimodal reasoning to provide **explainable authenticity reports** based on technical evidence from Google Cloud Vision and Video Intelligence APIs.

This project was built for the **Google BUILD & BLOG MARATHON 2025 – Hyderabad** to demonstrate state-of-the-art integrity verification.

## ✨ Core Innovation: Explainable AI

The primary value is the fusion of forensic data:

1.  **Feature Extraction:** Google Cloud Vision/Video Intelligence APIs extract low-level artifacts (anatomical asymmetry, temporal inconsistencies, compression flags).
2.  **Multimodal Reasoning:** **Gemini 1.5 Pro** synthesizes this raw data, assesses the correlation between artifacts, and generates a plain-language **Authenticity Report** with a final confidence rating.

---

## 🚀 Features

* **🧠 Gemini 1.5 Pro Reasoning:** Provides detailed, human-readable explanations of *why* content is flagged, increasing user trust.
* **🖼️ Multimodal Analysis:** Fuses data from **Google Cloud Vision API** (images) and **Google Video Intelligence API** (videos) for higher accuracy.
* **📈 Weighted Scoring:** Uses a custom weighted algorithm to prioritize highly reliable forensic indicators (e.g., temporal artifacts) over generic flags.
* **🖥️ Web Integration:** Designed for deployment on **Google Cloud Run** to provide a scalable, low-latency API endpoint for journalists and fact-checkers.

---

## 🛠️ Technology Stack

| Component | Technology | Purpose |
| :--- | :--- | :--- |
| **Reasoning Engine** | **Gemini 1.5 Pro (Vertex AI)** | Synthesizes all forensic artifacts and generates the final explainable report. |
| **Image Analysis** | **Google Cloud Vision API** | Extracts landmarks, asymmetry, and lighting properties. |
| **Video Analysis** | **Google Video Intelligence API** | Detects frame manipulation and temporal inconsistencies. |
| **Backend/Orchestration** | **Python (Cloud Run)** | Manages the full pipeline, file storage (GCS), and triggers API calls. |
| **Frontend/Hosting** | **React / Firebase Hosting** | User interface, file upload, and report display. |

---

## ⚙️ Installation & Setup

This project requires a Google Cloud Project with the necessary APIs enabled.

### Prerequisites

* Python 3.9+
* A Google Cloud Project with Billing Enabled.
* APIs Enabled: **Gemini API, Cloud Vision API, Cloud Video Intelligence API.**
* Authentication: Set up Google Cloud Application Default Credentials (ADC) or use a Service Account Key.

### Step 1: Clone the Repository

```bash
# Clone the repository
git clone [https://github.com/your-username/Gemini-TruthLens.git](https://github.com/your-username/Gemini-TruthLens.git)

# Navigate to the project directory
cd Gemini-TruthLens
# Install required Python packages for the orchestrator
pip install -r requirements.txt
# Example: Detect AI content in a video (using local ADC)
python main_analysis.py --file path/to/sample_media.mp4
{
  "confidence_score": 87,
  "is_fake": true,
  "gemini_report": "The content is highly likely synthetic (87%). Analysis detected significant asymmetry in facial landmarks (4.2° discrepancy) combined with unnatural temporal consistency. Verification should focus on the subject's right hand [Coordinates X,Y]."
}
