# AI-vs-ML-vs-Deep-Learning
# Description:
# Compare AI, ML, and Deep Learning, display examples,
# visualize their relationship, and demonstrate a simple
# Machine Learning model.
# ============================================================

import pandas as pd
import matplotlib.pyplot as plt
from sklearn.tree import DecisionTreeClassifier

# ------------------------------------------------------------
# 1. PROJECT INTRODUCTION
# ------------------------------------------------------------

print("=" * 65)
print("          AI vs ML vs DEEP LEARNING")
print("=" * 65)

print("""
Artificial Intelligence (AI):
AI enables machines to perform tasks that normally require
human intelligence.

Machine Learning (ML):
ML is a subset of AI that enables computers to learn patterns
from data and make predictions.

Deep Learning (DL):
DL is a subset of ML that uses multi-layer neural networks
to learn complex patterns.
""")

# ------------------------------------------------------------
# 2. COMPARISON TABLE
# ------------------------------------------------------------

data = {
    "Feature": [
        "Definition",
        "Scope",
        "Learning Method",
        "Data Requirement",
        "Main Goal",
        "Examples",
        "Applications"
    ],

    "Artificial Intelligence (AI)": [
        "Performs intelligent tasks",
        "Broadest field",
        "Rules, reasoning, search, or learning",
        "Depends on the approach",
        "Simulate intelligent behavior",
        "Rule-based expert systems",
        "Robotics and planning"
    ],

    "Machine Learning (ML)": [
        "Learns patterns from data",
        "Subset of AI",
        "Trains models using data",
        "Usually requires training data",
        "Learn patterns and make predictions",
        "Email spam detection",
        "Recommendations and fraud detection"
    ],

    "Deep Learning (DL)": [
        "Uses multi-layer neural networks",
        "Subset of ML",
        "Learns complex representations",
        "Often needs large datasets",
        "Learn complex patterns",
        "Image recognition",
        "Speech and image analysis"
    ]
}

df = pd.DataFrame(data)

print("\n1. COMPARISON TABLE")
print("-" * 65)
print(df.to_string(index=False))

# Display the table in a Jupyter Notebook
display(df)

# ------------------------------------------------------------
# 3. REAL-WORLD EXAMPLES
# ------------------------------------------------------------

examples = {
    "Artificial Intelligence (AI)": [
        "Rule-based expert systems",
        "Chess-playing programs",
        "Robotics planning",
        "Automated decision systems"
    ],

    "Machine Learning (ML)": [
        "Email spam detection",
        "Movie recommendations",
        "Credit card fraud detection",
        "Sales prediction"
    ],

    "Deep Learning (DL)": [
        "Face recognition",
        "Speech recognition",
        "Medical image analysis",
        "Object detection"
    ]
}

print("\n2. REAL-WORLD EXAMPLES")
print("-" * 65)

for technology, applications in examples.items():
    print(f"\n{technology}")

    for application in applications:
        print(f"  - {application}")

# ------------------------------------------------------------
# 4. VISUALIZE THE RELATIONSHIP BETWEEN AI, ML, AND DL
# ------------------------------------------------------------

print("\n3. RELATIONSHIP VISUALIZATION")
print("AI contains ML, and ML contains Deep Learning.")

fig, ax = plt.subplots(figsize=(10, 7))

# Outer rectangle represents AI
ai_rectangle = plt.Rectangle(
    (0.5, 0.5),
    9,
    6,
    facecolor="lightblue",
    edgecolor="blue",
    linewidth=2
)

# Middle rectangle represents ML
ml_rectangle = plt.Rectangle(
    (1.5, 1.0),
    7,
    4.5,
    facecolor="lightgreen",
    edgecolor="green",
    linewidth=2
)

# Inner rectangle represents Deep Learning
dl_rectangle = plt.Rectangle(
    (2.5, 1.5),
    5,
    2.5,
    facecolor="moccasin",
    edgecolor="darkorange",
    linewidth=2
)

ax.add_patch(ai_rectangle)
ax.add_patch(ml_rectangle)
ax.add_patch(dl_rectangle)

ax.text(
    0.8, 5.8,
    "Artificial Intelligence (AI)",
    fontsize=13,
    fontweight="bold"
)

ax.text(
    1.8, 4.8,
    "Machine Learning (ML)",
    fontsize=12,
    fontweight="bold"
)

ax.text(
    3.0, 2.5,
    "Deep Learning (DL)",
    fontsize=12,
    fontweight="bold"
)

ax.set_xlim(0, 10)
ax.set_ylim(0, 7)

ax.set_title(
    "Relationship Between AI, ML, and Deep Learning",
    fontsize=15,
    fontweight="bold"
)

ax.axis("off")
plt.tight_layout()
plt.show()

# ------------------------------------------------------------
# 5. SIMPLE MACHINE LEARNING MODEL
# ------------------------------------------------------------

print("\n4. MACHINE LEARNING DEMONSTRATION")
print("-" * 65)

# Sample input: number of hours studied
# This is a small, invented dataset for demonstration only.

X = [[1], [2], [3], [4], [5], [6]]

# Target labels:
# 0 = Fail
# 1 = Pass

y = [0, 0, 0, 1, 1, 1]

# Create the Decision Tree model
model = DecisionTreeClassifier(random_state=42)

# Train the model
model.fit(X, y)

print("Machine Learning model trained successfully.")

# Predict the result for a student who studied 4 hours
hours_studied = [[4]]

prediction = model.predict(hours_studied)[0]

if prediction == 1:
    result = "Pass"
else:
    result = "Fail"

print("Hours studied:", hours_studied[0][0])
print("Predicted result:", result)

# Make predictions for multiple values
test_hours = [[2], [3], [4], [5], [6]]

predictions = model.predict(test_hours)

print("\nPredictions for different study hours:")

for hours, prediction in zip(test_hours, predictions):
    result = "Pass" if prediction == 1 else "Fail"
    print(f"{hours[0]} hour(s) -> {result}")

# ------------------------------------------------------------
# 6. DISPLAY THE RELATIONSHIP IN TEXT
# ------------------------------------------------------------

print("\n5. RELATIONSHIP BETWEEN AI, ML, AND DL")
print("-" * 65)

print("""
Artificial Intelligence (AI)
    |
    └── Machine Learning (ML)
             |
             └── Deep Learning (DL)

AI is the broadest field.
ML is a subset of AI.
DL is a subset of ML.

Not all AI systems use ML.
Not all ML systems use Deep Learning.
""")

# ------------------------------------------------------------
# 7. CONCLUSION
# ------------------------------------------------------------

print("\n6. CONCLUSION")
print("-" * 65)

print("""
AI focuses on creating systems that perform intelligent tasks.

ML enables computers to learn patterns from data and make
predictions.

Deep Learning uses multi-layer neural networks to learn complex
patterns and representations.

These technologies have applications in healthcare, finance,
robotics, recommendations, speech recognition, and computer vision.

The relationship is:

AI > ML > Deep Learning
""")

print("=" * 65)
print("PROJECT COMPLETED SUCCESSFULLY")
print("=" * 65)
