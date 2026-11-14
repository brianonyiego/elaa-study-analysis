# ELAA Mixed-Methods Analysis

Python scripts for analysing a student questionnaire (n = 20) and a teacher semi-structured interview on the **English Language Activity-based Approach (ELAA)** in a Grade 10 senior high school class in Jiangsu Province, China.

The analysis follows a descriptive mixed-methods design (no inferential testing, because of the small sample) and triangulates questionnaire, interview and open-ended comment data.

## Repository contents

| File | Purpose |
|------|---------|
| `elaa_analysis.py` | Core analysis: Likert descriptives, composite scores, thematic coding, triangulation |
| `elaa_visual_analysis.py` | Eight matplotlib figures (descriptive and exploratory) |
| `elaa_figure_tables.py` | Text-only tables containing the numbers behind each figure |
| `requirements.txt` | Python dependencies |

## Requirements

- Python 3.9+
- `numpy`
- `matplotlib` (only for `elaa_visual_analysis.py`)
- `scikit-learn` (optional; used for the exploratory Random Forest. A correlation fallback is used if it is missing)

```bash
pip install -r requirements.txt
```

## How to run

```bash
python elaa_analysis.py
python elaa_visual_analysis.py
python elaa_figure_tables.py
```

- `elaa_analysis.py` and `elaa_figure_tables.py` print results to the terminal.
- `elaa_visual_analysis.py` opens interactive plot windows and prints supporting numbers.
- No files are read or written by any script.

## Questionnaire structure

| Construct | Items | Description |
|-----------|-------|-------------|
| Engagement | Q6-Q11 | Attention, enjoyment, motivation, collaboration, confidence, persistence |
| Communicative behaviour | Q12-Q16 | Speaking more, asking questions, responding to peers, sharing ideas |
| Student perceptions of ELAA | Q17-Q23 | Usefulness, preference, reduced fear, wanting more activities |

Responses are coded 1 (Strongly Disagree) to 5 (Strongly Agree). Q24 is an open-ended comment.

## Results

### 1. Construct-level descriptives (n = 20)

| Construct | Mean | SD | Min | Max |
|-----------|------|----|-----|-----|
| Engagement (Q6-Q11) | 3.99 | 0.66 | 2.83 | 5.00 |
| Communicative behaviour (Q12-Q16) | 3.76 | 0.60 | 2.80 | 5.00 |
| Student perceptions of ELAA (Q17-Q23) | 4.39 | 0.58 | 3.00 | 5.00 |

### 2. Item-level highlights

**Highest-rated items**

| Item | Mean | % Agree / Strongly Agree |
|------|------|--------------------------|
| Q19 ELAA helps me use English in real situations | 4.55 | 90% |
| Q20 I prefer ELAA to traditional lessons | 4.50 | 85% |
| Q17 Activities help me improve speaking | 4.45 | 90% |

**Lowest-rated items**

| Item | Mean | % Agree / Strongly Agree |
|------|------|--------------------------|
| Q13 I ask questions in English | 3.55 | 55% |
| Q16 I continue communicating despite missing words | 3.55 | 50% |
| Q10 I feel confident using English in tasks | 3.65 | 60% |

### 3. Group comparisons (descriptive only)

| Group | n | Mean overall Likert score |
|-------|---|---------------------------|
| Female | 11 | 4.09 |
| Male | 9 | 4.07 |
| Low speaking level | 4 | 3.93 |
| Intermediate speaking level | 13 | 3.97 |
| High speaking level | 3 | 4.74 |

Mean total questionnaire score: Female 73.55, Male 73.33.
No significance testing was performed. Group sizes are very small.

### 4. Exploratory correlations (not hypothesis tests)

| Relationship | Pearson r |
|--------------|-----------|
| Engagement and communicative behaviour | 0.74 |
| Communicative behaviour and perception | 0.71 |
| Engagement and perception | 0.56 |

### 5. Exploratory Random Forest item importance (illustrative only)

| Rank | Item | Importance |
|------|------|-----------|
| 1 | Q21 ELAA helps communicate with peers | 0.148 |
| 2 | Q17 Activities improve speaking | 0.102 |
| 3 | Q18 Activities more engaging | 0.096 |

With n = 20 and no held-out test set, this ranking is a discussion prompt, not a finding.

### 6. Teacher interview themes

| Theme | Type | Answers mentioning theme |
|-------|------|--------------------------|
| Peer support / collaboration | Inductive | 11 |
| Communicative behaviour | Deductive | 10 |
| Feasibility / implementation | Deductive | 8 |
| Engagement | Deductive | 8 |
| Exam pressure | Inductive | 7 |
| Novice-teacher scaffolding | Inductive | 4 |
| Confidence / anxiety | Inductive | 4 |
| Classroom management | Inductive | 4 |

### 7. Student open-ended comment themes (Q24)

| Theme | Mentions |
|-------|----------|
| Reduced pressure / anxiety | 9 |
| Group discussion / role-play preference | 9 |
| Enjoyment / fun | 8 |
| Real-life / practical use | 5 |
| Speaking confidence / willingness | 4 |

### 8. Triangulation summary

- **Engagement:** The questionnaire (mean 3.99/5), the teacher interview and student comments all point toward higher engagement during ELAA activities.
- **Communicative behaviour:** Questionnaire scores (mean 3.76/5) are consistent with the teacher's observations of students asking questions, responding to peers and negotiating meaning. This was the lowest-scoring construct.
- **Contradiction check:** No student showed both low communicative behaviour (< 3.0) and high perception (>= 4.0).
- **Feasibility:** The teacher reported ongoing constraints (exam pressure, classroom management, novice-teacher confidence) alongside positive evaluations.

## Limitations

- Small sample (n = 20) and a single teacher interview
- No control group, so no causal claims can be made
- Descriptive statistics only; correlations and the Random Forest are exploratory
- Keyword-based thematic coding is a supporting tool and does not replace manual qualitative coding

## Data and ethics

The scripts contain embedded participant responses. Make sure that sharing this repository is consistent with the study's ethics approval and participant consent. Anonymise or remove identifying details (such as the school name) before making it public.

## License

Add a license here (e.g. MIT) if you make the repository public.
