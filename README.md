# python--screening--task-3
## Step-Up (Setup) Instructions

Install Python

Install Python 3.10+ from the official website or package manager.

During installation, ensure “Add Python to PATH” is selected on Windows.

Create a virtual environment

macOS/Linux: python3 -m venv venv

Windows: py -m venv venv

Activate the environment

macOS/Linux: source venv/bin/activate

Windows (PowerShell): .\venv\Scripts\Activate

Install helpful tools

Linters/formatters: pip install ruff black

Type checking: pip install mypy

Debugging support (optional): pip install ipdb

Verify versions

python --version

pip list

Editor configuration

Use VS Code or a similar editor with Python, Pylance, and Debugger extensions enabled.

Turn on “Format on Save” and linting in editor settings.
### 1. Finding and Shortlisting Models
- Explore open-source, code-focused models such as:
  - BigCode/StarCoder family
  - Meta’s CodeGen variants
  - CodeBERT and CodeT5
  - Lightweight models like GPT-NeoX
- Criteria for selection:
  - Trained on code or code+text
  - Licensed for research and teaching
  - Can run locally or on a modest cloud GPU

### 2. Testing and Validating Models
- Test models on:
  - Short Python programs from students
  - Buggy code rewritten differently
  - Conceptual programming questions

- For each task, check if the model can:
  - Summarize code functionality
  - Identify errors in student thinking
  - Ask helpful, non-spoiling questions

- Validation:
  - Automatic checks (Bloom’s level, solution leak detection, explanation quality)
  - Teacher reviews (clarity, insight, spoiler avoidance)
  - Classroom trial (compare model hints vs. generic hints, measure quiz improvement)

### 3. Balancing Accuracy, Clarity, and Cost
- Bigger models = better understanding but higher cost
- Smaller models = cheaper but less detailed
- Large models = less interpretable, simpler models = more transparent
- Explanation increases compute time; balance speed and interpretability

### 4. Why StarCoder (BigCode) Is a Good Choice
- Strong Python understanding, instruction-style prompts, teaching adaptation
- Limitations (solution leak, hallucinations, compute needs) can be mitigated with prompt design, human review, and model selection
### Reasoning
Choosing and Testing Code-Understanding Models
Main Takeaway: Use open-source code-focused models like StarCoder that are easy to run, licensed for research, and test them with real student code and teacher feedback to make sure they help students learn without giving away answers.

1. Finding and Shortlisting Models
Look at free models designed to work with code, such as:

BigCode/StarCoder family

Meta’s CodeGen variants

CodeBERT and CodeT5

Lightweight models like GPT-NeoX

Pick ones that:

Were trained on code or code+text

Have licenses allowing research and teaching

Can run on your computer or a modest cloud GPU

Once you have a shortlist, give each model three types of tasks that mimic real classroom work:

Short Python programs from students (some correct, some with mistakes)

Buggy code rewritten in different words

Conceptual questions about programming ideas

For each task, see if the model can:

Summarize what the student’s code does

Spot where their thinking went wrong

Ask helpful questions that guide the student without giving the full solution

2. Testing and Validating Models
Combine automatic checks with teacher reviews:

Automatic Checks

Bloom’s Level: Use an embedding-based classifier to see if the model’s questions match the expected level (e.g., “understand,” “apply,” “analyze”).

No Solution Leaks: Measure text overlap between the model’s question and the actual solution—lower overlap means fewer accidental spoilers.

Quality of Explanations: Compare model-generated feedback to instructor-written feedback.

Teacher Reviews
Have instructors or teaching assistants rate each question on:

Clarity

How well it reveals student thinking

Whether it accidentally gives away the answer

Then run a small classroom test: give some students the model’s scaffolded questions and others standard generic hints. Measure their improvement on a follow-up quiz and gather feedback on how useful the questions were.

3. Balancing Accuracy, Clarity, and Cost
Every choice has trade-offs:

Accuracy vs. Cost: Bigger models usually understand code better but cost more to run. Smaller or quantized models save money but may miss details.

Accuracy vs. Interpretability: Large models can be black boxes, so it’s hard to see why they made a mistake. Simpler or rule-based systems are easier to understand but less flexible.

Interpretability vs. Speed: Asking a model to explain its reasoning adds compute time, which can slow down real-time feedback.

Decide based on your setting. For instructor tools, you might pick the most accurate model. For automated class-wide feedback, you might choose a faster, cheaper model.

4. Why StarCoder (BigCode) Is a Good Choice
Strengths:

Built on large code datasets, so it understands Python well.

Responds to instruction-style prompts, making it easy to ask “diagnose,” “hint,” or “question” tasks.

Can be fine-tuned or use adapters to focus on teaching.

Limitations and Fixes:

Solution Leakage: Control it with careful prompt design, filters, or by training on scaffolded examples.

Hallucinations: Set confidence thresholds, add human review steps, or combine model output with static code analysis.

Compute Needs: Use smaller, distilled versions or quantized checkpoints for faster, lighter inference.

By carefully testing and tuning, you can ensure StarCoder provides helpful, non-spoiling feedback that truly supports student learning.
