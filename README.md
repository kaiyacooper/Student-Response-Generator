# Response Generator

![License: MIT](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)
![Built with: Python](https://img.shields.io/badge/Built%20with-Python-blue?style=flat-square)
![Platform: Google Colab](https://img.shields.io/badge/Platform-Google%20Colab-orange?style=flat-square)
![Uses: OpenAI API](https://img.shields.io/badge/Uses-OpenAI%20API-teal?style=flat-square)

An AI-powered Python script that generates large sets of realistic, uniquely-named written responses for research, testing, and data collection purposes.

---

## Why I Built This

I originally built this to generate a batch of sample written responses for a workshop. I needed a large set of varied, realistic submissions from different "students" quickly. Instead of writing them manually or picking 200 unique names, I automated the whole thing. The script uses AI to write each response and a name generator to give every one a unique identity.

---

## What It Does

Run the script and it will automatically:

1. Generate a unique fictional name for each response
2. Randomize background attributes (like familiarity level and usage habits) to vary the perspective
3. Use an AI model to write a realistic, human-sounding response based on those attributes
4. Save each response as its own `.txt` file
5. Zip everything up and download it when done

---

## Features

- **Bulk Generation:** Produces a large number of unique responses in one run with no manual work
- **Randomized Identities:** Uses [Faker](https://faker.readthedocs.io/en/master/) to assign a different name to every response
- **Varied Perspectives:** Randomly assigns attributes per response so the output isn't repetitive
- **Auto-Retry Logic:** Skips and retries any response that doesn't meet the minimum quality check
- **Packaged Output:** All files are saved, zipped, and downloaded automatically at the end

---

## Use Cases

This tool is useful for anyone who needs a lot of varied, realistic text responses at once:

- Populating a test database or demo app with realistic fake data
- Generating training or evaluation data for NLP/ML models
- Prototyping a survey analysis pipeline before real responses come in
- Creating anonymized stand-ins to replace real submissions in shared research
- Running a workshop, exercise, or classroom activity that needs sample submissions

---

## The Prompt

<details>
<summary>Click to see the full prompt</summary>

```
Write a 200–300 word open-ended reflection from a fictional college student named {name}.
The student is enrolled in 'CTS4935: Ethics and Society in AI' and is submitting an assignment
titled 'Reflection on Artificial Intelligence' dated {date}. The student has {familiarity}
familiarity with AI and {does/does not} use AI in daily life. The response should be personal,
thoughtful, and realistic—like a college student writing a professional short essay with limited
nuances. Include their name at the top, followed by the date, course name, and assignment title.
Do not list metadata separately—embed familiarity and usage naturally into the reflection.
Avoid generic phrasing and starting with 'When I first'. Make it sound like a real college
student with a unique and professional voice.
```

</details>

---

## Stack

- Python 3
- [Faker](https://faker.readthedocs.io/en/master/)
- OpenAI API
- Google Colab

---

## Setup

### Prerequisites

You'll need an API key from an AI provider (this script uses OpenAI by default). If you want to swap in a different provider, the API call is isolated to one function and easy to change.

### Steps

**1. Open the script in Google Colab**

Upload the `.py` file or paste the code into a new Colab notebook.

**2. Install dependencies**

```bash
%pip install faker openai
```

**3. Add your API key**

At the top of the script, replace the placeholder with your actual key:

```python
TOOLKIT_API_KEY = "your-api-key-here"
BASE_URL = "https://your-api-endpoint/"
```

**4. Run all cells**

The script will loop automatically until it reaches the target count. Progress is printed as it saves each file.

**5. Download your results**

When finished, a `.zip` of all responses will automatically download from Colab.

---

## Output

Each response is saved as `FirstName_LastName.txt`, word-wrapped at 80 characters. All files are collected in a single folder and zipped for easy download.

---

> **Disclaimer:** All responses are AI-generated. The names are fictional and created by Faker — any resemblance to real people is coincidental. Always review AI output before using it in any official or published context.

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
