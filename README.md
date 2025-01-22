# How to create recruitment insights using Python!
You don’t need to be super knowledgable in tech to use Python for recruitment. With just a few lines of code, you can:
- Find out how long it really takes to hire someone.
- See which job boards bring in the best candidates.
- Figure out when you’ll get the most applications, so you can plan ahead.

Here’s how to get started:

**1. Install Python and the right tools**

First, download Python from [python.org](https://www.python.org/downloads/) and install a few key tools by running this command in your terminal:

```bash
pip install pandas matplotlib seaborn

```

Think of it like grabbing coffee before a long meeting—you need the basics to stay productive.

**2. Load your recruitment data**

Export your hiring data from your ATS or spreadsheets and load it into Python like this:

```python
import pandas as pd

df = pd.read_csv("recruitment_data.csv")
print(df.head())  # See the first few rows

```

This helps you get a clear view of your hiring trends.

**3. Spot trends with simple charts**

Want to see how applications change over time? Try this:

```python
import matplotlib.pyplot as plt
import seaborn as sns

df['Application Date'] = pd.to_datetime(df['Application Date'])
df['Month'] = df['Application Date'].dt.to_period('M')
monthly_apps = df.groupby('Month').size()

plt.figure(figsize=(10,5))
sns.lineplot(x=monthly_apps.index.astype(str), y=monthly_apps.values, marker="o")
plt.title('Applications Over Time')
plt.xlabel('Month')
plt.ylabel('Number of Applications')
plt.xticks(rotation=45)
plt.show()

```

It’s like checking your bank statements to spot spending habits—data reveals patterns.

**4. Measure your hiring sources**

Curious if LinkedIn, referrals, or job ads work best? Try this:

```python
source_counts = df['Source'].value_counts()
source_counts.plot(kind='bar', color='skyblue')
plt.title('Applicants by Source')
plt.xlabel('Source')
plt.ylabel('Number of Applicants')
plt.show()

```

Now you’ll know where to focus your efforts (and budget).

**5. Figure out your time-to-hire**

Want to know how long it takes to fill a position? Let Python do the math:

```python
avg_time_to_hire = df['Time-to-Hire'].mean()
print(f'Average Time to Hire: {avg_time_to_hire} days')

```

If it's taking longer than expected, you’ll know where to adjust.

---

The best part? Python is free, easy to learn, and packed with online resources. If you’re curious, check out this free EdX course: [RaspberryPi: Learn Python!](https://www.edx.org/learn/computer-programming/raspberry-pi-foundation-teach-teens-computing-programming-in-python?utm_source=rpf_website_python_pathway&utm_medium=partner-marketing&utm_campaign=raspberrypifoundation) 


Let’s make recruitment a bit more predictable, shall we? 
