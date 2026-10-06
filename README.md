# 🎧 Customer Support Ticket Analyzer
 
A Python-based ticket analysis system that stores, cleans, analyses, and extracts insights from customer support tickets using only core Python (dictionaries, lists, sets, strings, and functions).
 
> **Module-End Assignment — Data Analytics (DA), Module 4: Python**
 
---
 
## 📌 Problem Statement
 
Customer support teams handle numerous service tickets every day. Analysing these tickets helps identify:
 
- Common issues raised by customers
- Customer sentiment (positive / negative feedback)
- Support quality
- Areas for improvement
This project builds a command-line tool that takes raw, messy ticket text and turns it into clean, analysable data with useful summary insights.
 
---
 
## ✨ Features
 
| Step | Feature | Description |
|------|---------|-------------|
| 1 | **Preloaded Tickets** | Starts with 10 sample tickets stored as a dictionary of lists and prints them in a readable format |
| 2 | **Add New Tickets** | Asks the user how many tickets to add, then collects name, description and priority |
| 3 | **Text Cleaning** | Removes punctuation, extra spaces, converts to lowercase, and replaces slang |
| 4 | **Keyword Insights** | `count_tickets_with_word(word)` counts tickets containing a keyword (case-insensitive) |
| 5 | **Final Summary** | Priority breakdown, longest description, and unique word analysis |
 
---
 
## 🗂️ Data Structure
 
All tickets live in a single dictionary of lists:
 
```python
ticket_data = {
    'Ticket_No':         [1, 2, 3, ...],
    'Customer_Name':     ['Ravi', 'Meera', 'Sam', ...],
    'Issue_Description': [' Internet not working!!! ', ...],
    'Priority':          ['High', 'Low', 'High', ...]
}
```
 
Each index position across the four lists represents one ticket.
 
---
 
## 🔄 How It Works
 
### Step 1 — Preloaded Tickets
The program begins with 10 predefined tickets and prints them in a readable, row-by-row format.
 
### Step 2 — Add More Tickets
- Prompts: *"How many new tickets do you want to add?"*
- For each new ticket, collects **Customer Name**, **Issue Description**, and **Priority**
- **Ticket numbers auto-increment** starting from `11`
- **Priority validation:** only `High`, `Medium`, or `Low` is accepted (re-prompts otherwise)
- New data is appended to `ticket_data`
### Step 3 — Text Cleaning
Every issue description is cleaned by:
1. Removing punctuation (`. , ! ? -`)
2. Converting multiple spaces into a single space
3. Stripping leading/trailing spaces
4. Converting text to lowercase
5. Replacing slang/shorthand (e.g. `ok` → `okay`)
**Example**
 
| Before | After |
|--------|-------|
| `' Internet not working!!! '` | `internet not working` |
| `'GREAT support! issue resolved.'` | `great support issue resolved` |
 
Methods used: `.replace()`, `.split()`, `' '.join()`, `.strip()`, `.lower()`
 
### Step 4 — Keyword-Based Issue Insights
 
```python
def count_tickets_with_word(word):
    ...
```
 
- Case-insensitive search
- Returns the number of ticket descriptions containing the given word
Used to report the number of tickets containing:
`poor` · `good` · `slow` · `excellent`
 
### Step 5 — Final Summary & Insights
1. **Final cleaned `ticket_data`** — nicely formatted dictionary-of-lists output
2. **Priority analysis** — count of High, Medium, and Low priority tickets
3. **Longest issue description** (by word count) — prints ticket number, customer name, cleaned text, and word count
4. **Unique words** — a `set` of all unique words across descriptions, showing the count and the sorted word list
---
 
## 🚀 Getting Started
 
### Prerequisites
- Python 3.x (no external libraries required)
### Installation

 
### Run
 
```bash
python ticket_analyzer.py
```
 
### Sample Interaction
 
```text
How many new tickets do you want to add? 1
Enter Customer Name: Priya
Enter Issue Description: App keeps crashing, pls fix!!
Enter Priority (High/Medium/Low): urgent
Invalid priority! Please enter High, Medium, or Low.
Enter Priority (High/Medium/Low): High
```
 
---
 
## 📁 Project Structure
 
```text
customer-support-ticket-analyzer/
│
├── ticket_analyzer.py   # Main program
└── README.md            # Project documentation
```
 
---
 
## 🧰 Concepts Used
 
- Dictionaries and lists (dictionary of lists)
- String methods: `.strip()`, `.lower()`, `.replace()`, `.split()`, `' '.join()`
- Functions with parameters and return values
- Loops and conditionals
- Input validation
- Sets for unique value extraction
- Sorting
---
 
## 📊 Sample Insights Produced
 
- Count of tickets mentioning `poor`, `good`, `slow`, `excellent`
- Number of High / Medium / Low priority tickets
- The ticket with the most detailed (longest) description
- Total number of unique words and the full sorted vocabulary
---
 
## 🔮 Possible Improvements
 
- Add sentiment scoring (positive / negative / neutral)
- Remove stop words (`the`, `and`, `is`) before unique-word analysis
- Save results to a CSV file
- Visualise priority distribution with a bar chart
- Build a Pandas version of the analyzer
---
 
## 👤 Author
 
**Revathi**
---
 
## 📄 License
 
This project is created for educational purposes as part of a Data Analytics course assignment.
 
