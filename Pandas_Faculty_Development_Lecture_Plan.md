# Pandas for Business School Faculty: Lecture Plan
## "From Data Chaos to Data Clarity: Your Journey with Pandas"

**Instructor:** Aykut Firat  
**Duration:** 60 minutes  
**Target Audience:** Sawyer Business School Faculty  
**Platform:** Zoom + Google Colab

---

## Session Overview

**Main Learning Objective:** Empower faculty to confidently handle, explore, and visualize their research and teaching datasets using Pandas and Google Colab.

**The Promise:** By the end of this session, you'll be able to:
- Import and explore any dataset in minutes
- Clean messy data like a pro
- Create publication-ready visualizations
- Answer complex research questions with just a few lines of code

---

## Session Structure (60 Minutes)

### Part 1: Teaching & Demonstration (30 minutes)
### Part 2: Hands-On Practice (15 minutes)
### Part 3: Solution Review & Wrap-Up (15 minutes)

---

## PART 1: TEACHING & DEMONSTRATION (30 Minutes)

### Opening Hook (2 minutes)
**"The Faculty Research Reality Check"**

*Start with a relatable scenario:*

"Imagine this: You've collected survey data from 500 MBA students. It's in Excel. There are missing values. Some columns have typos. You need to analyze it by demographic groups, create visualizations for your paper, and... Excel just crashed. Sound familiar?"

**The Good News:** "What if I told you that with Pandas, you could handle a dataset of 500,000 rows as easily as 500, never lose your work, reproduce your analysis with one click, and create stunning visualizations? And it's all FREE."

---

### Module 1: "The Pandas Power Trio" (7 minutes)

#### 1A. Google Colab: Your Free Data Science Lab (2 min)
**Key Points:**
- No installation needed - just a browser
- Free computing power (including GPUs!)
- Shareable like Google Docs
- Auto-saves your work

**Demo:** 
- Open a new Colab notebook
- Show the interface: cells, comments, running code
- "This is your research notebook - code, visualizations, and notes all in one place"

#### 1B. What is Pandas? (2 min)
**The Simple Story:**
- "Think of Pandas as Excel on steroids... but smarter, faster, and more reproducible"
- Two main structures: Series (column) and DataFrame (table)
- Built for business analysis: financial data, surveys, customer data, etc.

**Visual Analogy:**
```
Excel Spreadsheet → Pandas DataFrame
Excel Column → Pandas Series
Excel Formulas → Pandas Methods (but way more powerful!)
```

#### 1C. Your First Pandas Commands (3 min)

**Live Demo - The Essential Four:**

```python
import pandas as pd

# 1. READ - Load your data
df = pd.read_csv('your_data.csv')

# 2. LOOK - See what you've got
df.head()

# 3. UNDERSTAND - Get the summary
df.info()

# 4. ANALYZE - Quick statistics
df.describe()
```

**Faculty Connection:**
"These four commands answer: What data do I have? Is it clean? What are the patterns? - The first questions in ANY research project."

---

### Module 2: "Data Exploration for Research" (8 minutes)

#### 2A. Loading Real Business Data (2 min)

**Demo with Business-Relevant Dataset:**
Use a MBA salary survey or similar dataset

```python
# Load a real business dataset
df = pd.read_csv('https://raw.githubusercontent.com/...')

# What's in here?
print(f"Dataset shape: {df.shape[0]} rows and {df.shape[1]} columns")
df.columns
```

**Faculty Insight:**
"Notice we used a URL? You can pull data directly from the internet, from Google Sheets, from databases... no manual downloading!"

#### 2B. Asking Business Questions with Pandas (6 min)

**The Research Question Framework:**

**Question 1: "What are my variables?"**
```python
# See all column names
df.columns

# Check data types
df.dtypes
```

**Question 2: "Are there missing values?"**
```python
# Missing data check
df.isnull().sum()

# Visual check
import seaborn as sns
sns.heatmap(df.isnull(), cbar=False)
```

**Question 3: "What are the basic statistics?"**
```python
# For numerical columns
df.describe()

# For specific column
df['Salary'].mean()
df['Department'].value_counts()
```

**Faculty Application:**
- Survey response rates? → `df.isnull().sum()`
- Average scores by group? → `df.groupby('Group')['Score'].mean()`
- Distribution of responses? → `df['Answer'].value_counts()`

---

### Module 3: "Data Cleaning & Transformation" (7 minutes)

#### 3A. Filtering Your Data (3 min)

**Business Scenarios:**

```python
# Scenario 1: Filter high-performing students
high_performers = df[df['GPA'] > 3.5]

# Scenario 2: Multiple conditions (AND)
international_high_gpa = df[(df['International'] == True) & (df['GPA'] > 3.5)]

# Scenario 3: Filter by category (OR)
target_industries = df[df['Industry'].isin(['Tech', 'Finance', 'Consulting'])]

# Scenario 4: Text search
boston_companies = df[df['Location'].str.contains('Boston')]
```

**Faculty Connection:**
"These filters let you segment your data for analysis - by demographic, by response type, by time period - just like you'd do in SPSS or Stata, but more flexibly."

#### 3B. Creating New Variables (2 min)

```python
# Create a new column
df['Salary_Thousands'] = df['Salary'] / 1000

# Categorize continuous data
df['Salary_Category'] = pd.cut(df['Salary'], 
                                bins=[0, 50000, 75000, 100000, 200000],
                                labels=['Entry', 'Mid', 'Senior', 'Executive'])

# Combine columns
df['Full_Name'] = df['First_Name'] + ' ' + df['Last_Name']
```

#### 3C. Handling Missing Data (2 min)

```python
# Strategy 1: Drop rows with ANY missing values
df_clean = df.dropna()

# Strategy 2: Drop rows with missing values in SPECIFIC columns
df_clean = df.dropna(subset=['Important_Column'])

# Strategy 3: Fill missing values
df['Age'].fillna(df['Age'].median(), inplace=True)

# Strategy 4: Fill with category
df['Department'].fillna('Unknown', inplace=True)
```

---

### Module 4: "Visualization for Insights" (6 minutes)

#### 4A. Quick Pandas Plots (3 min)

```python
# Bar chart - Categorical data
df['Department'].value_counts().plot(kind='bar')
plt.title('Students by Department')
plt.show()

# Histogram - Distribution
df['Salary'].plot(kind='hist', bins=20)
plt.title('Salary Distribution')
plt.show()

# Box plot - Compare groups
df.boxplot(column='Salary', by='Department')
plt.show()
```

#### 4B. Beautiful Visualizations with Seaborn (3 min)

```python
import seaborn as sns
import matplotlib.pyplot as plt

# Set style
sns.set_style("whitegrid")

# Visualization 1: Relationship between variables
sns.scatterplot(data=df, x='GPA', y='Starting_Salary', hue='Major')
plt.title('GPA vs Starting Salary by Major')
plt.show()

# Visualization 2: Compare groups
sns.boxplot(data=df, x='Department', y='Salary')
plt.xticks(rotation=45)
plt.title('Salary Distribution by Department')
plt.show()

# Visualization 3: Correlation heatmap
correlation_matrix = df[['GPA', 'Salary', 'Experience']].corr()
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm')
plt.title('Variable Correlations')
plt.show()
```

**Faculty Impact:**
"These are publication-ready visualizations. No more fighting with Excel charts. Copy, paste into your paper, done."

---

## PART 2: HANDS-ON PRACTICE (15 Minutes)

### The Practice Challenge: "MBA Salary Analysis"

**Context:** "You're analyzing MBA program outcomes. Your dataset contains information about graduates: their background, program experience, and job outcomes."

### Exercise Instructions:

```
You'll work with real MBA salary data. Your tasks:

1. Load and explore the dataset
2. Clean the data (handle missing values)
3. Answer three research questions:
   - What's the average salary by industry?
   - Which factors correlate with higher salaries?
   - How do international vs domestic students compare?
4. Create visualizations to tell the story

The practice notebook has specific prompts and hints!
```

### Faculty Support During Practice:
- Monitor Zoom chat for questions
- Share screen to help stuck participants
- Encourage pair-programming in breakout rooms if needed
- Remind: "There's no one right way - explore!"

---

## PART 3: SOLUTION REVIEW & WRAP-UP (15 Minutes)

### Solution Walkthrough (10 minutes)

**Philosophy:** Show multiple approaches to the same problem

#### Example: Question 1 - Average Salary by Industry

**Solution Approach A (Beginner-friendly):**
```python
industry_salaries = df.groupby('Industry')['Salary'].mean()
print(industry_salaries)
```

**Solution Approach B (With Visualization):**
```python
industry_salaries = df.groupby('Industry')['Salary'].mean().sort_values()
industry_salaries.plot(kind='barh', figsize=(10, 6))
plt.title('Average Salary by Industry')
plt.xlabel('Average Salary ($)')
plt.show()
```

**Solution Approach C (Publication-ready):**
```python
import seaborn as sns

plt.figure(figsize=(12, 6))
sns.barplot(data=df, x='Industry', y='Salary', ci=95)
plt.xticks(rotation=45, ha='right')
plt.title('Average Salary by Industry (with 95% CI)', fontsize=14)
plt.ylabel('Salary ($)', fontsize=12)
plt.tight_layout()
plt.show()
```

**Teaching Moment:**
"Notice how we went from a simple answer to a sophisticated visualization? That's the beauty of Pandas - you start simple, add complexity as needed."

---

### Key Takeaways & Next Steps (5 minutes)

#### The "Faculty Five" - Five Things You Can Do Tomorrow:

1. **Import your current research data into Colab**
   - CSV, Excel, Google Sheets - all work!

2. **Use `.describe()` and `.info()` to understand your data**
   - Replace your manual data checking

3. **Create one visualization with Seaborn**
   - Better than Excel, faster than PowerPoint

4. **Filter your data for specific analysis**
   - Segment your survey responses, filter by criteria

5. **Share your notebook with collaborators**
   - Reproducible research made easy!

#### Resources for Continued Learning:

**Essential Bookmarks:**
- Pandas Cheat Sheet: [pandas.pydata.org/docs](https://pandas.pydata.org/docs)
- Seaborn Gallery: [seaborn.pydata.org/examples](https://seaborn.pydata.org/examples)
- Google Colab Guide: [colab.research.google.com](https://colab.research.google.com)

**Practice Datasets:**
- Our course collection: [Link to Suffolk GitHub]
- Kaggle datasets: [kaggle.com/datasets](https://kaggle.com/datasets)
- World Bank data: [data.worldbank.org](https://data.worldbank.org)

**SAIL Support:**
- Office hours: [Schedule]
- Slack channel: #pandas-help
- Follow-up workshop: Advanced Pandas (Date TBD)

#### Final Thought:

"Remember: Every expert was once a beginner. The faculty who master these tools aren't necessarily more technical - they're just more curious and more persistent. You've taken the first step today. The data world is now open to you."

**Call to Action:**
- "Before Friday: Load one of your datasets into Colab"
- "Share your first visualization in our Slack channel"
- "Email me with questions - I'm here to help!"

---

## Instructor Notes for Aykut

### Presentation Tips:

**Energy & Engagement:**
- Start with high energy - this overcomes "tech anxiety"
- Use humor: "If I can do this, anyone can!"
- Acknowledge frustration: "Yes, the syntax is weird at first. That's normal!"

**Pacing:**
- Check in every 5 minutes: "Everyone with me?"
- Use Zoom polls: "Who's done with step 3?"
- Have backup examples ready if moving too fast

**Common Questions to Anticipate:**

1. **"How is this different from Excel?"**
   - "Excel is great for viewing. Pandas is great for analyzing at scale and reproducing your work."

2. **"Do I need to know programming?"**
   - "You need to know three things: read, copy, modify. That's it."

3. **"What if I get errors?"**
   - "Errors are normal! Google the error message - someone else has had it."

4. **"Is this really free?"**
   - "Yes! Google Colab is completely free. So is Pandas."

5. **"Can I use this for [specific research]?"**
   - "Almost certainly yes. Let's talk after!"

### Technical Preparation:

**Before Session:**
- [ ] Test all code examples in fresh Colab notebook
- [ ] Prepare backup datasets in case URLs fail
- [ ] Have solutions ready in separate notebook
- [ ] Clear your Colab environment (log out/in)
- [ ] Test screen sharing with Zoom
- [ ] Have Chat GPT or Claude open for live error debugging

**During Session:**
- [ ] Share practice notebook link at minute 30
- [ ] Post solutions link at minute 45
- [ ] Save chat questions for FAQ document

**After Session:**
- [ ] Send follow-up email with:
  - Recording link
  - Notebook links
  - Additional resources
  - Office hours schedule
- [ ] Create FAQ document from questions
- [ ] Schedule follow-up workshop

### Adaptation Strategies:

**If Running Behind:**
- Skip detailed Seaborn examples (just show one)
- Reduce practice time to 10 minutes
- Show solutions without full walkthrough

**If Running Ahead:**
- Add bonus topic: Reading from Google Sheets
- Show more advanced filtering (query method)
- Demo the `.agg()` function for multiple statistics

**If Participants Struggling:**
- Switch to follow-along mode (stop independent practice)
- Use Zoom breakout rooms for peer help
- Simplify practice questions on the fly

### Success Metrics:

**During Session:**
- 80%+ successfully load a dataset
- 60%+ complete at least one practice question
- 90%+ say "this seems useful"

**Post-Session:**
- 40%+ try with their own data within a week
- 25%+ attend follow-up session
- 10%+ integrate into their course/research

### Follow-Up Workshop Ideas:

1. **"Pandas for Survey Analysis"** - Likert scales, factor analysis prep
2. **"Data Visualization Masterclass"** - Publication-ready plots
3. **"Statistical Analysis with Pandas + Statsmodels"** - Regression, ANOVA
4. **"Automating Research Tasks"** - Batch processing, report generation

---

## Session Success Story (Tell at beginning):

"Last semester, a finance professor came to me frustrated. She had 10 years of stock market data in 50 different Excel files. She needed to analyze patterns, but Excel kept crashing. We spent 30 minutes with Pandas. We loaded all 50 files, combined them into one dataset, ran her analysis, and created all her charts. What would have taken her weeks took 30 minutes. That's why we're here today."

---

## Closing Quote:

*"The goal is to turn data into information, and information into insight." - Carly Fiorina*

"Today, you've learned the tools to do exactly that. Welcome to the world of data-powered research and teaching!"

---

**End of Lecture Plan**

*Prepared for: SAIL Faculty Development Series*  
*Instructor: Aykut Firat*  
*Version: 1.0*  
*Date: November 2025*
