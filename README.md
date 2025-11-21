# 💡 Gemini Content Origin: AI Media Authenticity Checker

Gemini Content Origin is a tool designed to analyze media and determine its authenticity and originality. It leverages the multimodal capabilities of the **Gemini API** to check content and identify synthetic or AI-generated media.

This project was built to demonstrate effective use of the Gemini platform for content verification.

---

## 🚀 Features

* **🧠 Gemini API Integration:** Uses the **Gemini 1.5 Pro** model for multimodal reasoning and content analysis.
* **🖼️ Content Authenticity Check:** Determines if media content appears original or synthetically generated.
* **🌐 Multimodal Analysis:** Capable of checking both image and video files for signs of modification or AI generation.
* **📈 Confidence Scoring:** Provides a percentage score indicating the confidence level of the originality assessment.

---

## 🛠️ Technology Stack

| Component | Technology | Purpose |
| :--- | :--- | :--- |
| **Analysis Engine** | **Gemini 1.5 Pro** | The core model used to analyze media files and assess originality. |
| **Backend/Orchestration** | **Python** | Manages file processing and coordinates calls to the Gemini API. |
| **File Handling** | **Google Cloud Storage (GCS)** | Used for temporarily storing media files before analysis. |

---

## ⚙️ Installation & Setup

This project requires access to the Gemini API.

### Prerequisites

* Python 3.9+
* A project with access to the **Gemini API**.
* Authentication: Your `GEMINI_API_KEY` set as an environment variable.

### Step 1: Clone the Repository

```bash
# Clone the repository
git clone [https://github.com/your-username/Gemini-Content-Origin.git](https://github.com/your-username/Gemini-Content-Origin.git)

# Navigate to the project directory
cd Gemini-Content-Origin
# Install required Python packages
pip install -r requirements.txt
# Set your Gemini API Key
export GEMINI_API_KEY="YOUR_API_KEY"

# Run the originality check on an image file
python main_analysis.py --file path/to/image.jpg
Originality Assessment: Synthetically Generated
Confidence Score: 92%
Gemini Conclusion: The content exhibits high regularity in texture and lacks natural photo noise, suggesting a high likelihood of AI generation.
