# AgentK8s – EKS Operational Review Tool

AgentK8s is a Streamlit-based EKS (Elastic Kubernetes Service) Operational Review Agent built using the [AgentPro](https://github.com/traversaal/AgentPro) framework. It conducts intelligent reviews of your EKS clusters and generates a categorized prescriptive action plan.

## 🚀 Features

- Interactive conversational UI for step-by-step review
- Categorized recommendations (short-term, medium-term, long-term)
- Intelligent backend reasoning with Ares agent (internet & video search)
- Risk dashboards and visual metrics
- PDF export of review reports with best practices

## 🏗️ Architecture

```
Streamlit UI ──► AgentK8s (AgentPro) ──► Ares Tool ──► Google & YouTube Search
                                             │
                                             └─► Action Plan Generator ──► PDF/Charts
```

## 🔧 Installation

1. Clone the repository

```bash
git clone https://github.com/yourorg/agentk8s.git
cd agentk8s
```

2. Set up a virtual environment and install dependencies

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

3. Create a `.env` file with the required API keys:

```env
TRAVERSAAL_ARES_API_KEY=your_api_key_here
OPENAI_API_KEY=your_openai_key_here
```

## 🔑 Environment Variables

This project requires the following environment variables:

- `TRAVERSAAL_ARES_API_KEY`: **Required**  
  This key is used to enable [Ares](https://www.traversaal.com/ares), a knowledge agent in AgentPro, to perform intelligent internet searches (including Google and YouTube) and recommend best practices for EKS based on the user's inputs.  
  > You can get an API key from [Traversaal](https://www.traversaal.com/ares).

- `OPENAI_API_KEY`: **Required**  
  This key enables the AgentPro framework to perform reasoning and language generation using OpenAI models.

## ▶️ Running the Tool

```bash
streamlit run app/main.py
```

The app will be available at `http://localhost:8501`

## 📄 Output Example

After completing the review, you will receive:
- A categorized EKS operational review
- Risk breakdowns by area (e.g., cost, security)
- A downloadable PDF with recommendations and action items

## 📁 Project Structure

```
agentk8s/
├── agents/
│   └── agentk8s.py         # Main review logic
├── app/
│   └── main.py             # Streamlit UI
├── assets/
├── utils/
│   └── pdf_generator.py    # PDF report creation
│   └── charts.py           # Visualization helpers
├── requirements.txt
├── .env
└── README.md
```

## 🤝 Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## 👥 Contributors

- Pravinkumar Menghani  
- Qais Poonawala

## 🛡️ License

[MIT](./LICENSE)

