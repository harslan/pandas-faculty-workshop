# 🐼 Pandas Faculty Development Workshop

> **From Data Chaos to Data Clarity: A hands-on workshop for business school faculty**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/)
[![Made with Love](https://img.shields.io/badge/Made%20with-❤️-red.svg)](https://suffolk.edu)

**Live Workshop Site:** [https://YOUR-USERNAME.github.io/pandas-faculty-workshop/](https://YOUR-USERNAME.github.io/pandas-faculty-workshop/)

---

## 📋 Overview

A complete, ready-to-deliver 60-minute faculty development workshop teaching Pandas for data analysis. Designed specifically for business school faculty with zero coding experience.

### 🎯 Learning Outcomes

By the end of this workshop, faculty will be able to:
- Load and explore datasets using Pandas in Google Colab
- Handle missing data appropriately for research
- Filter and segment data using conditions
- Calculate summary statistics by groups
- Create publication-ready visualizations
- Apply these skills to their own research data

---

## 🚀 Quick Start for Faculty

### Option 1: Use the Workshop Website
Visit our [workshop website](https://YOUR-USERNAME.github.io/pandas-faculty-workshop/) for easy access to all materials.

### Option 2: Direct Downloads
1. **Download All Materials:** [Pandas_Faculty_Workshop_Complete.zip](https://github.com/YOUR-USERNAME/pandas-faculty-workshop/raw/main/Pandas_Faculty_Workshop_Complete.zip)
2. **Open Google Colab:** [colab.research.google.com](https://colab.research.google.com/)
3. **Upload notebooks** (the .ipynb files)
4. **Start learning!** 🎉

### Option 3: Clone This Repository
```bash
git clone https://github.com/YOUR-USERNAME/pandas-faculty-workshop.git
cd pandas-faculty-workshop
```

---

## 📦 Repository Contents

```
pandas-faculty-workshop/
│
├── index.html                                   # Workshop website (GitHub Pages)
├── README.md                                     # This file (GitHub README)
│
├── 00_Quick_Start_Guide.md                      # Instructor prep checklist
├── Pandas_Faculty_Development_Lecture_Plan.md   # Detailed session plan
├── ONE_PAGE_SUMMARY.md                          # Quick reference card
│
├── 01_Teaching_Demonstration_Notebook.ipynb     # Teaching content (30 min)
├── 02_Practice_Exercises_Notebook.ipynb         # Student practice (15 min)
├── 03_Solutions_with_Explanations.ipynb         # Solutions (15 min)
│
└── Pandas_Faculty_Workshop_Complete.zip         # All files bundled
```

---

## ⏱️ Workshop Structure

### Part 1: Teaching & Demonstration (30 minutes)
**Notebook:** `01_Teaching_Demonstration_Notebook.ipynb`

- Module 1: Setup & Basics (9 min)
- Module 2: Data Exploration (8 min)  
- Module 3: Data Cleaning (7 min)
- Module 4: Visualization (6 min)

### Part 2: Hands-On Practice (15 minutes)
**Notebook:** `02_Practice_Exercises_Notebook.ipynb`

Independent work with guided exercises and hints

### Part 3: Solutions & Wrap-Up (15 minutes)
**Notebook:** `03_Solutions_with_Explanations.ipynb`

Review solutions, discuss takeaways, next steps

---

## 🎓 For Instructors

### Prerequisites
- Google account (for Colab)
- Zoom meeting setup
- Web browser
- No software installation required!

### Preparation Checklist
1. ✅ Read `00_Quick_Start_Guide.md`
2. ✅ Review `Pandas_Faculty_Development_Lecture_Plan.md`
3. ✅ Test all notebooks in Google Colab
4. ✅ Get shareable links for each notebook
5. ✅ Practice opening hook and transitions

### Getting Shareable Links
For each notebook in Google Colab:
1. File → Share
2. Change to "Anyone with the link can view"
3. Copy and save the link

### Delivery Tips
- Start with high energy to overcome tech anxiety
- Show mistakes - it normalizes struggling
- Connect every example to faculty research
- One person trying Pandas = success!

---

## 🎯 Topics Covered

### Pandas Operations
- Reading CSV files from URLs
- `.head()`, `.tail()`, `.info()`, `.describe()`
- Checking data types and dimensions
- Identifying and handling missing values
- Filtering with single/multiple conditions
- Creating new calculated columns
- Grouping and aggregation (`.groupby()`)

### Visualization
- Basic Pandas plots (hist, bar, box)
- Seaborn visualizations (barplot, boxplot, heatmap)
- Multi-panel dashboards
- Publication-ready formatting

### Business Applications
- Survey response analysis
- Salary and compensation studies
- Customer segmentation
- Performance metrics by group
- Correlation analysis

---

## 🌐 Setting Up GitHub Pages

### Option 1: Enable GitHub Pages (Recommended)
1. Go to your repository Settings
2. Navigate to "Pages" section
3. Under "Source", select "Deploy from a branch"
4. Choose "main" branch and "/ (root)" folder
5. Click Save
6. Your site will be live at: `https://YOUR-USERNAME.github.io/pandas-faculty-workshop/`

### Option 2: Using gh-pages Branch
```bash
git checkout -b gh-pages
git push origin gh-pages
```
Then follow Option 1 steps, selecting "gh-pages" branch instead.

### Customizing the Website
Edit `index.html` to customize:
- University branding/colors
- Contact information  
- Links to your Colab notebooks
- Add your own examples

---

## 📚 Additional Resources

### Official Documentation
- **Pandas:** https://pandas.pydata.org/docs
- **Seaborn:** https://seaborn.pydata.org/examples
- **Google Colab:** https://colab.research.google.com

### Practice Datasets
- **Kaggle:** https://kaggle.com/datasets
- **UCI ML Repository:** https://archive.ics.uci.edu
- **World Bank:** https://data.worldbank.org

### Community Support
- Stack Overflow (pandas tag)
- r/learnpython subreddit
- Pandas Discord server

---

## 🤝 Contributing

We welcome contributions! Here's how you can help:

### Bug Reports & Feature Requests
Open an issue describing:
- The problem or enhancement
- Steps to reproduce (for bugs)
- Your environment (browser, OS)

### Pull Requests
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Areas for Contribution
- Additional practice exercises
- Alternative datasets (especially business-focused)
- Translations
- Accessibility improvements
- Video tutorials
- Advanced workshops (follow-up content)

---

## 📊 Success Metrics

### During Workshop
- ✅ 80%+ successfully load a dataset
- ✅ 60%+ complete ≥1 practice exercise
- ✅ 90%+ find content useful

### Post-Workshop (1 week)
- ✅ 40%+ try with their own data
- ✅ 25%+ attend follow-up sessions

### Long-term (1 month)
- ✅ 10%+ integrate into research/teaching

---

## 🎯 The Faculty Five

Encourage faculty to try these five things within a week:

1. **Import research data** into Google Colab
2. **Use `.describe()` and `.info()`** to understand data
3. **Create one visualization** with Seaborn
4. **Filter data** for specific analysis
5. **Share notebook** with collaborators

---

## 📧 Contact & Support

**Workshop Created By:** Aykut Firat  
**Institution:** Suffolk University Sawyer Business School  
**Initiative:** SAIL (Social Intelligence, AI Literacy, Innovation/Inquiry, Leadership) Collaborative

**Questions?** Open an issue or contact: afirat@suffolk.edu

---

## 📜 License

This workshop is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

**Summary:** You are free to use, modify, and distribute this workshop with attribution.

---

## 🙏 Acknowledgments

**Created For:**
- Suffolk University Sawyer Business School
- SAIL Collaborative Faculty Development

**Inspired By:**
- Pandas community tutorials
- Data Science teaching best practices
- Real faculty research needs

**Built With:**
- 💙 Love for education
- 🐼 Pandas library
- 🎨 Modern web standards
- 🤝 Community feedback

---

## 📈 Version History

### v1.0.0 (November 2025)
- Initial release
- Complete 60-minute workshop
- Three Jupyter notebooks
- Comprehensive documentation
- GitHub Pages website

---

## 🌟 Star This Repository!

If you find this workshop useful, please star ⭐ this repository to help others discover it!

---

## 🔄 Updates & Improvements

We're continuously improving this workshop based on feedback. Check back for:
- 📝 Additional exercises
- 🎥 Video tutorials
- 🌍 Multi-language support
- 📊 Advanced follow-up workshops
- 🤖 AI/ML integration modules

---

## 💬 Feedback

We'd love to hear from you! Please:
- ⭐ Star this repo if it helped
- 🐛 Report bugs via Issues
- 💡 Suggest improvements
- 📣 Share your success stories
- 🤝 Contribute enhancements

---

**Made with ❤️ for faculty by faculty**

*"The goal is to turn data into information, and information into insight." - Carly Fiorina*

---

**Ready to transform your data analysis?** [🚀 Start the workshop now!](https://YOUR-USERNAME.github.io/pandas-faculty-workshop/)
