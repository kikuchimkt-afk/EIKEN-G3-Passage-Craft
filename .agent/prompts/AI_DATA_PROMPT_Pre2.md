# AI Data Generation Prompt for Eiken Grade Pre-2 (Passage 3B)

You are an expert Eiken (Test in Practical English Proficiency) content creator.
Your task is to analyze the provided Grade Pre-2 (Level A2+/B1) Reading Passage and generate an **original, high-quality, and highly similar** problem based on its structure, difficulty, and logic.

## 1. Analysis of Input Data
Analyze the following from the provided past exam:
- **Topic:** Environment, Science, Culture, Daily Life, etc.
- **Word Count:** Usually 280–330 words.
- **Paragraph Structure:** Logic flow (e.g., Intro -> Details/history -> Impact -> Conclusion).
- **Question Logic:** Identify which paragraph/sentence serves as the evidence for each of the questions (usually 4-5 questions).

## 2. Design Guidelines for Original Problem
- **Difficulty:** CEFR A2+ / Eiken Grade Pre-2. Sentences should be slightly simpler than Grade 2 but clearer and strictly logical.
- **Word Count:** Target 280–330 words.
- **Topic Imitation:** Maintain the same category as the input but change the specific subject.
  - *Example:* If past exam is "Salt (History/Uses)", create original "Spices (History/Uses)".
- **Paragraph Logic:** Mimic the past exam's flow exactly.
- **Strict Formatting & 1:1 Translation Sync:**
  - **Sentence Formatting:** Ensure every sentence ends with a punctuation mark followed by **exactly one half-width space**.
  - **No mid-sentence line breaks.**
  - **Translations:** You MUST provide a 1:1 mapping between English sentences and Japanese translations.
- **Question Design:**
  - Create the same number of questions as the input (usually 4).
  - **Evidence location must match** the past exam (e.g., Q1 evidence is in Para 1).
  - Use a different Answer Key pattern than the input.

## 3. Output Format
Output ONLY the code blocks below. **Do not include any conversational filler.**

### [Block 1: AVAILABLE_YEARS]
```javascript
{ year: YYYY, session: S, label: "YYYY-S (Topic Name)" },
```

### [Block 2: MOCK_DATA Entry]
```javascript
  "YYYY-S": {
    past: {
      title: "Past Exam Title",
      content: `## Title: Past Exam Title\n\n[Full OCR Text of Past Exam]`,
      questions: `### Questions\n\n**(1) Question Text**\n1. Option\n2. Option\n...\n\n---\n**Answer Key:** (1) X, (2) Y, (3) Z, (4) W`,
      translations: [
        { en: "Past sentence 1", ja: "過去問訳1" },
        { en: "Past sentence 2", ja: "過去問訳2" }
      ]
    },
    original: {
      title: "Original Title",
      content: `## Title: Original Title\n\n[Original AI-Generated Text]`,
      questions: `### Questions\n\n**(1) Question Text**\n1. Option\n2. Option\n...\n\n---\n**Answer Key:** (1) X, (2) Y, (3) Z, (4) W`,
      translations: [
        { en: "Original sentence 1", ja: "オリジナル作成訳1" },
        { en: "Original sentence 2", ja: "オリジナル作成訳2" }
      ]
    },
    analysis: {
      intent: `## 作成意図・根拠 (Blueprint)

**ターゲットモデル:** [Past Exam Title] ([Topic]) の構造模倣

### 1. 量的構造

- **総単語数:** 約 [Word Count] words
- **パラグラフ構成:**
  1. **導入:** [Contemporary situation vs Past situation, etc.]
  2. **[Theme 1]:** [Details corresponding to Para 2]
  3. **[Theme 2]:** [Details corresponding to Para 3]
  4. **結論:** [Conclusion corresponding to Para 4]

### 2. 重要語彙

- **[Word 1]:** [Meaning 1]
- **[Word 2]:** [Meaning 2]
- **[Word 3]:** [Meaning 3]
- **[Word 4]:** [Meaning 4]
- **[Word 5]:** [Meaning 5]
...`,
      summary: `## 講師用：本文要約 (Instructor Summary)

<div style="font-size: 1.2rem; font-weight: bold; margin-top: 1.5rem; color: black;">[Past Exam Title] (過去問)</div>

<p>[Brief overview of the entire passage's main point and flow].</p>

<h3 class="summary-section-header">1. Introduction (第1段落)</h3>
<p>[Detailed summary of Para 1 in Japanese. Explain the setup/intro clearly.]</p>

<h3 class="summary-section-header">2. [Para 2 Title] (第2段落)</h3>
<p>[Detailed summary of Para 2. Focus on specific examples or arguments.]</p>

<h3 class="summary-section-header">3. [Para 3 Title] (第3段落)</h3>
<p>[Detailed summary of Para 3. Focus on economic/social impact or historical context.]</p>

<h3 class="summary-section-header">4. [Para 4 Title] (第4段落)</h3>
<p>[Detailed summary of Para 4. Focus on modern relevance or conclusion.]</p>

<hr style="margin: 2rem 0;">

<div style="font-size: 1.2rem; font-weight: bold; margin-top: 1.5rem; color: black;">[Original Title] (オリジナル)</div>

<p>[Brief overview of the entire passage's main point and flow].</p>

<h3 class="summary-section-header">1. Introduction (第1段落)</h3>
<p>[Detailed summary of Para 1 in Japanese.]</p>

<h3 class="summary-section-header">2. [Para 2 Title] (第2段落)</h3>
<p>[Detailed summary of Para 2.]</p>

<h3 class="summary-section-header">3. [Para 3 Title] (第3段落)</h3>
<p>[Detailed summary of Para 3.]</p>

<h3 class="summary-section-header">4. [Para 4 Title] (第4段落)</h3>
<p>[Detailed summary of Para 4.]</p>

---
講師用資料：授業前の確認や、生徒への解説の構成案としてご活用ください。`,
      comparison: `
<h3 class="comparison-section-header">過去問との比較分析 (Category Comparison)</h3>

<div style="overflow-x: auto;">
  <table class="comparison-table">
    <thead>
      <tr>
        <th>項目</th>
        <th>[Past Title] (過去問)</th>
        <th>[Original Title] (オリジナル)</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="font-bold">テーマ</td>
        <td>...</td>
        <td>...</td>
      </tr>
      <tr>
        <td class="font-bold">構造</td>
        <td>
          1. ...<br>
          2. ...<br>
          3. ...<br>
          4. ...
        </td>
        <td>
          1. ...<br>
          2. ...<br>
          3. ...<br>
          4. ...
        </td>
      </tr>
      <tr>
        <td class="font-bold">共通点</td>
        <td colspan="2">
          ・...<br>
          ・...
        </td>
      </tr>
      <tr>
        <td class="font-bold">相違点</td>
        <td>
          第3段落：...<br>
          第4段落：...
        </td>
        <td>
          第3段落：...<br>
          第4段落：...
        </td>
      </tr>
    </tbody>
  </table>
</div>

<h3 class="comparison-section-header">1. トピックと展開の相違 (Topic Differences)</h3>

<ul>
  <li>
    <strong>[Past Title] (過去問):</strong>
    <ul>
      <li><strong>Focus:</strong> [Focus explanation]</li>
    </ul>
  </li>
  <li style="margin-top: 1rem;">
    <strong>[Original Title] (オリジナル):</strong>
    <ul>
      <li><strong>Focus:</strong> [Focus explanation]</li>
    </ul>
  </li>
</ul>

<h3 class="comparison-section-header">2. 設問設計の比較 (Question Design)</h3>

<ul>
  <li>
    <strong>Q26 (内容一致 - Para 1):</strong>
    <ul>
      <li><strong>過去問:</strong> "[Quote]" (Explanation)</li>
      <li><strong>Original:</strong> "[Quote]" (Explanation)</li>
    </ul>
  </li>
  <li style="margin-top:10px;">
    <strong>Q27 (内容一致 - Para 2):</strong>
    <ul>
      <li><strong>過去問:</strong> ...</li>
      <li><strong>Original:</strong> ...</li>
    </ul>
  </li>
  <li style="margin-top:10px;">
    <strong>Q28 (内容一致 - Para 3):</strong>
    <ul>
      <li><strong>過去問:</strong> ...</li>
      <li><strong>Original:</strong> ...</li>
    </ul>
  </li>
  <li style="margin-top:10px;">
    <strong>Q29 (内容一致 - Para 4):</strong>
    <ul>
      <li><strong>過去問:</strong> ...</li>
      <li><strong>Original:</strong> ...</li>
    </ul>
  </li>
</ul>`,


      syntax: `## 4. 正解の根拠となるセンテンスの構文解析
<div style="font-size: 1.5rem; font-weight: bold; color: #1e293b; margin-bottom: 0.5rem;">[Past Exam Title] (過去問)</div>

<p style="margin-bottom: 2rem;"><span style="font-weight:bold; color:#000;">[Strategy Note]</span> [Explain the strategy clearly]</p>

<h4 class="syntax-question-header">【設問1の根拠】 (正解: [X])</h4>
<p><strong>Q:</strong> [Question Summary JP]</p>
<p><strong>A:</strong> [Correct Answer Summary JP]</p>

<div class="syntax-panel syntax-panel-evidence">
  <span style="font-weight:bold;">Evidence:</span> "[Quote sentence] <strong>[Main Verb]</strong> ..."
</div>

<div class="syntax-panel syntax-panel-structure">
  <ul style="margin: 0; padding-left: 1.2rem;">
    <li><strong>主語 (S):</strong> ...</li>
    <li><strong>動詞 (V):</strong> ...</li>
    <li><strong>修飾:</strong> ...</li>
  </ul>
</div>

<div class="syntax-panel syntax-panel-point">
  [Explain the grammar point/logic]
</div>

<h4 class="syntax-question-header">【設問2の根拠】 (正解: [X])</h4>
...

<br><hr><br>

<div style="font-size: 1.5rem; font-weight: bold; color: #1e293b; margin-bottom: 0.5rem;">[Original Title] (オリジナル)</div>

<p style="margin-bottom: 2rem;"><span style="font-weight:bold; color:#000;">[Strategy Note]</span> ...</p>

...`
    }
  },
```

## 4. Key Constraints for Pre-2nd Grade
- **Syntax Analysis / HTML Structure:**
  - You **MUST** use valid HTML formatting for the `syntax` field. Do not use Markdown for the boxes.
  - **Headers:** `<h4 class="syntax-question-header">【設問Xの根拠】 (正解: X)</h4>`
  - **Evidence:** `<div class="syntax-panel syntax-panel-evidence"><span style="font-weight:bold;">Evidence:</span> "..."</div>`
  - **Structure:** `<div class="syntax-panel syntax-panel-structure"><ul style="margin: 0; padding-left: 1.2rem;"><li><strong>主語 (S):</strong> ...</li>...</ul></div>`
  - **Point:** `<div class="syntax-panel syntax-panel-point">...</div>`
- **Bolding Rules (Strict):**
  - **Evidence:** **BOLD** only the main verb(s) using `<strong>` (e.g., `it <strong>is</strong> used`).
  - **Structure:** **BOLD** the labels (e.g., `<strong>動詞 (V):</strong>`) but NOT the content value.
- **Summary Styling:**
  - You **MUST** generate `summary` content for **BOTH** texts: `[Past Title] (過去問)` AND `[Original Title] (オリジナル)`.
  - Use specific headers for summaries: `<h3 class="summary-section-header">1. Introduction (第1段落)</h3>`
  - For title separators, use: `<div style="font-size: 1.2rem; font-weight: bold; margin-top: 1.5rem; color: black;">[Title] (Category)</div>`
- **Comparison Styling:**
  - You **MUST** use the `<table class="comparison-table">` structure for the main comparison.
  - You **MUST** include two additional sections below the table:
    1. `<h3 class="comparison-section-header">1. トピックと展開の相違 (Topic Differences)</h3>` with a `<ul>` list.
    2. `<h3 class="comparison-section-header">2. 設問設計の比較 (Question Design)</h3>` with a `<ul>` list detailing Q26-Q29 (or Q34-Q37) contrasts.
  - Use `<td class="font-bold">` for the first column (Theme, Structure, etc.).
  - Use `<h3 class="comparison-section-header">` for the main title.
- **Dual Analysis:**
  - Generate full analysis for **BOTH** Past and Original passages.
