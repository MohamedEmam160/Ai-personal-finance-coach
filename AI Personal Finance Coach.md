# 🚀 [Tips Hindawi](https://www.tipshindawi.com/) Challenge (June–July) 2026

> 🏆 This repository is my official submission for the [ **Tips Hindawi** ](https://www.tipshindawi.com/) **Challenge (June–July) 2026**.

## 👤 Participant

| Field            | Value                                |
| ---------------- | ------------------------------------ |
| Full Name        | Mohamed Emam                         |
| Project Name     | AI Personal Finance Coach            |
| GitHub Username  | MohamedEmam160                       |
| Challenge Batch  | June–July 2026                       |
| Training Program | Large Language Models (LLMs) Program |
| Organization     | [**Edrak for Ai**](https://edrak4ai.com/en) |

---

# 📖 Project Overview

**AI Personal Finance Coach** is an AI-powered financial assistant built with **LangGraph**. It walks a user's financial data (income, expenses, savings, debt, and goals) through a pipeline of specialized AI agents that analyze spending, detect wasteful spending patterns, build a personalized savings/investment plan, run "what-if" scenario simulations, and generate a complete financial report — exported as a downloadable PDF.

Unlike typical LLM-based projects that depend on a paid API key, this project runs entirely on a **free, open-source model (Qwen2.5-3B-Instruct)** loaded locally on a free Google Colab GPU, making it fully reproducible at zero cost.

---

# ✨ Features

* **Financial Analyzer Agent** — scores the user's overall financial health (0–100) with a short AI-generated assessment.
* **Expense Categorizer Agent** — automatically classifies raw transactions into standard categories (Housing, Food, Transportation, Entertainment, etc.).
* **Leakage Detector Agent** — flags specific areas of unnecessary or excessive spending.
* **RAG-style Context Retriever** — supplies relevant budgeting/investment guidance based on the user's current situation.
* **Cash Flow Forecasting Tool** — projects monthly cash flow and savings growth over a chosen time horizon.
* **Financial Planner Agent** — produces a concrete savings target, investment strategy, and goal timeline.
* **Scenario Simulation Agent** — models "what-if" scenarios (e.g., job loss, salary increase) and their financial impact.
* **Report Generator Agent** — compiles every agent's output into a structured report and exports it as a **PDF**.
* **Zero paid API cost** — powered by a free, locally-run open-source LLM instead of OpenAI.

---

# 🛠️ Technologies Used

* **Python**
* **LangGraph** — orchestrates the multi-agent workflow as a state graph
* **LangChain Core** — prompt templates and message handling
* **Hugging Face Transformers** — loads and runs the local open-source LLM
* **Qwen2.5-3B-Instruct** — free, open-source instruction-tuned language model
* **PyTorch** — model inference on GPU
* **ReportLab** — PDF report generation
* **Pandas / NumPy** — data handling
* **Google Colab (T4 GPU)** — free runtime environment
* **FAISS** — vector storage groundwork for retrieval-augmented context

---

# ⚙️ Installation

1. Open the notebook (`AI_Personal_Finance_Coach.ipynb`) in **Google Colab**.
2. Set the runtime to a GPU instance: `Runtime → Change runtime type → T4 GPU`.
3. Run the install cell at the top of the notebook to install all required packages.
4. **Restart the runtime** (`Runtime → Restart session`) once, as instructed in the notebook — this avoids known Colab dependency conflicts with `numpy`/`Pillow`.
5. Run the remaining cells in order. The local model (`Qwen2.5-3B-Instruct`) will download automatically the first time — no API key required.

---

# 🚀 Usage

1. Run all cells from the configuration section down through the agent/tool definitions.
2. Build and compile the LangGraph workflow (`Financial Analyzer → Expense Categorizer → Leakage Detector → RAG Context Retriever → Financial Planner → Simulation Agent → Report Generator`).
3. Define a `FinanceState` with your own data (age, country, currency, income, expenses, savings, debt, goals), or use the provided sample state.
4. Run `graph.invoke(test_state)` to execute the full pipeline.
5. Review the printed summary, and find the full report at `reports/Financial_Report.pdf`.
6. (Optional) Call `simulation_agent` directly with a custom scenario dictionary to explore additional what-if cases without re-running the whole graph.

---

# 📸 Demo

Below is a sample of the generated `Financial_Report.pdf` for a test user (income 5000 EGP, expenses 2500 EGP, savings 10000 EGP, goals: buy a house / save for retirement):

<details>
<summary>📄 Click to expand sample report output</summary>

```
AI Personal Finance Coach - Comprehensive Financial Report

1. Overall Summary
The user's financial score is 45 out of 100, indicating room for improvement in managing expenses and
increasing savings. The cashflow is positive at 2500 EGP per month, with a focus on reducing shopping
and entertainment expenses.

2. Financial Health Score & Details
Score: 45/100
The financial health score is moderate, suggesting that the user should focus on better managing
expenses, particularly on high spending categories like shopping and entertainment. The user's
immediate goal is to save more by cutting down these expenses and increasing their monthly saving
target to 318 EGP.

3. Expense Analysis
Categorized Expenses:
- Housing: 1000.00 EGP
- Food: 300.00 EGP
- Transportation: 50.00 EGP
- Utilities: 100.00 EGP
- Entertainment: 120.00 EGP
- Shopping: 250.00 EGP
- Other: 0.00 EGP

4. Leakage Insights
- High shopping expenses (Shopping: 250.00 EGP)
- Consider reducing entertainment budget (Entertainment: 120.00 EGP)

5. Saving Plan Details
Current savings: 10000.0 EGP | Monthly saving target: 318.0 EGP | Recommended savings rate: 20%
Goal timeline: Buy a house (3-5 years), Save for retirement (20+ years)

6. Investment Strategy & Recommendations
Start small but consistent with a mix of short-term and long-term savings, considering a balanced
portfolio including stocks, bonds, and possibly real estate investments for long-term strategy.

7. Goal Progress Notes
The user has made significant progress in saving for a house and retirement, but there is room for
improvement in managing expenses and increasing the savings rate to meet long-term goals.

8. Simulation Results Summary
The baseline check indicates that the individual is already saving at a rate of 20% of their income,
which is commendable towards achieving their goals. The simulation suggests that the user should
continue with the current savings strategy as it aligns well with reaching short-term goals like buying a
house.

9. Actionable Recommendations
- Reduce high spending categories like shopping and entertainment.
- Set up automatic transfers into a savings or investment account.
- Monitor and review expenses monthly to identify areas for cost reduction.
- Increase the monthly saving target to 318 EGP.
- Consider a balanced investment portfolio including stocks, bonds, and real estate for long-term growth.

10. Important Notes
- Use the 50/30/20 rule to categorize expenses (50% needs, 30% wants, 20% savings/debt).
- Review and adjust spending categories monthly to stay on track.
- Monitor cashflow and expenses closely to ensure alignment with financial goals.
```

</details>

---

# 📈 Results

* Successfully processes a sample user profile end-to-end through all seven agents with no manual intervention.
* Produces a categorized expense breakdown, a list of detected spending leakages, a 24-month cash flow forecast, a personalized savings/investment plan, and a scenario simulation.
* Generates a polished, multi-section PDF report summarizing all findings.
* Runs entirely on free infrastructure (Colab's free GPU tier + an open-source model), with no paid API dependency.

---

# 🔮 Future Improvements

* Replace the placeholder RAG retriever with a real vector database (FAISS/Chroma) over actual financial guidance documents.
* Add a simple front-end (e.g., Streamlit or FastAPI) so users can input their data without editing the notebook.
* Support real transaction data import from bank statement PDFs/CSVs via `pdfplumber`.
* Add conditional/branching logic in the graph (e.g., skip leakage detection if no transactions are provided).
* Experiment with larger or fine-tuned local models for more accurate structured JSON outputs.

---

# 📚 About the Challenge

This project was developed as part of the [**Tips Hindawi**](https://www.tipshindawi.com/) **Challenge (June–July) 2026**.

[Tips Hindawi](https://www.tipshindawi.com/) is the internships department of [**Edrak for Ai**](https://edrak4ai.com/en), and the challenge encourages participants to build real-world projects, apply practical skills, and showcase their work through GitHub.

For more information about the challenge, training programs, and upcoming batches, visit the official [Tips Hindawi](https://www.tipshindawi.com/) website.

---

# 📄 License

This project is shared for educational and portfolio purposes.
