---
description: Workflow for integrating and formatting new exam data into mockData.js
---

# Integrate Exam Data Workflow

This workflow outlines the steps to add new exam data (e.g., "grade3-2025-2", "pre2-2024-1") to the PassageCraft application.

## 1. Preparation

1.  **Identify Target Grade Level**:
    *   **3級 (Grade 3)**: Use `src/data/grade3Data.js`
    *   **準2級 (Pre-2nd Grade)**: Use `src/data/gradePre2Data.js`

2.  **Analyze Source Data**:
    *   Identify the Exam ID format: `{grade}-{year}-{session}` (e.g., `grade3-2025-2`, `pre2-2024-1`)
    *   Extract the "Past Exam" title and "Original Exam" title.
    *   Ensure all data fields are available:
        *   `past`: { title, content, questions, translations }
        *   `original`: { title, content, questions, translations }
        *   `analysis`: { intent, summary, comparison, syntax }

## 2. Data Structure

### 2.1 Content Format (content, questions)

**IMPORTANT: 過去問に脚注（*印）がある場合は、本文末に追加すること**

```javascript
content: `## Title: [Title Name]

[Paragraph 1 text]

[Paragraph 2 text]

[Paragraph 3 text]

[Paragraph 4 text]

---
*word1: 日本語訳1
*word2: 日本語訳2`,
questions: `### Questions

**(26) [Question text]**
1. [Option 1]
2. [Option 2]
3. [Option 3]
4. [Option 4]

// ... more questions ...

---
**Answer Key:** (26) X, (27) X, ...`
```

> [!NOTE]
> 脚注は`---`（水平線）で区切り、`*単語: 日本語訳`の形式で追加します。
> 例: `*engine: エンジン`、`*Native American: アメリカ先住民（の）`

### 2.2 Translations Format
```javascript
translations: [
  { en: "English sentence 1.", ja: "日本語文1。" },
  { en: "English sentence 2.", ja: "日本語文2。" },
  // ... all sentences from the content
]
```

### 2.3 Analysis - Intent (作成意図・根拠)
```javascript
intent: `## 作成意図・根拠 (Blueprint)

**ターゲットモデル:** [過去問タイトル] (Category) の構造模倣 (英検X級レベル)

### 1. 量的構造
- **総単語数:** 約 XXX words
- **パラグラフ構成:**
  1. **導入:** [概要]
  2. **歴史:** [概要]
  3. **現在:** [概要]
  4. **課題:** [概要]

### 2. 重要語彙
- **word1:** 意味
- **word2:** 意味`
```

### 2.4 Analysis - Summary (本文要約) - HTML Format
```javascript
summary: `
<div style="font-size: 1.2rem; font-weight: bold; margin-top: 1.5rem; color: black;">[過去問タイトル] (過去問)</div>

[概要説明文]

### 1. 導入 (Introduction)
[段落1の要約]

### 2. 歴史 (History/Origin)
[段落2の要約]

### 3. 現在 (Present)
[段落3の要約]

### 4. 課題 (Controversy)
[段落4の要約]


<div style="font-size: 1.2rem; font-weight: bold; margin-top: 1.5rem; color: black;">[オリジナルタイトル] (オリジナル)</div>

[同様の構造で...]

---
講師用資料：授業前の確認や、生徒への解説の構成案としてご活用ください。`
```

### 2.5 Analysis - Comparison (過去問との比較) - **CRITICAL: HTML Table Format**

**MANDATORY**: Use HTML table with `comparison-table` class, NOT Markdown tables.

```javascript
comparison: `
<h3 class="comparison-section-header">過去問との比較分析 (Category Comparison)</h3>

<div style="overflow-x: auto;">
  <table class="comparison-table">
    <thead>
      <tr>
        <th>項目</th>
        <th>[過去問タイトル] (過去問)</th>
        <th>[オリジナルタイトル] (オリジナル)</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td class="font-bold">テーマ</td>
        <td>[過去問テーマ]</td>
        <td>[オリジナルテーマ]</td>
      </tr>
      <tr>
        <td class="font-bold">構造</td>
        <td>
          1. 導入：[概要]<br>
          2. 起源：[概要]<br>
          3. 現在：[概要]<br>
          4. 批判：[概要]
        </td>
        <td>
          1. 導入：[概要]<br>
          2. 起源：[概要]<br>
          3. 現在：[概要]<br>
          4. 批判：[概要]
        </td>
      </tr>
      <tr>
        <td class="font-bold">共通点</td>
        <td colspan="2">
          ・[共通点1]<br>
          ・[共通点2]<br>
          ・[共通点3]
        </td>
      </tr>
      <tr>
        <td class="font-bold">相違点</td>
        <td>[過去問の相違点]</td>
        <td>[オリジナルの相違点]</td>
      </tr>
    </tbody>
  </table>
</div>

<h3 class="comparison-section-header">1. トピックと展開の相違 (Topic Differences)</h3>

<ul>
  <li>
    <strong>[過去問タイトル] (過去問):</strong>
    <ul>
      <li><strong>Topic:</strong> [テーマ説明]。</li>
      <li><strong>Focus:</strong> [フォーカス説明]。</li>
    </ul>
  </li>
  <li style="margin-top: 1rem;">
    <strong>[オリジナルタイトル] (オリジナル):</strong>
    <ul>
      <li><strong>Topic:</strong> [テーマ説明]。</li>
      <li><strong>Focus:</strong> [フォーカス説明]。</li>
    </ul>
  </li>
</ul>

<h3 class="comparison-section-header">2. 設問設計の比較 (Question Design)</h3>

<ul>
  <li>
    <strong>Q26 (内容一致 - Para 1):</strong>
    <ul>
      <li><strong>過去問:</strong> "[本文からの引用]" ([説明])。</li>
      <li><strong>Original:</strong> "[本文からの引用]" ([説明])。</li>
    </ul>
  </li>
  <li style="margin-top:10px;">
    <strong>Q27 (内容一致 - Para 2):</strong>
    <ul>
      <li><strong>過去問:</strong> "[本文からの引用]" ([説明])。</li>
      <li><strong>Original:</strong> "[本文からの引用]" ([説明])。</li>
    </ul>
  </li>
  <!-- Q28, Q29, Q30 も同様に -->
</ul>`
```

### 2.6 Analysis - Syntax (構文解説) - **HTML Format with Panels**

```javascript
syntax: `## 4. 正解の根拠となるセンテンスの構文解析

# [過去問タイトル] (過去問)

> **[Strategy Note for Grade X]** [戦略的アドバイス]

## 【設問26の根拠】(正解: X)
**Q:** [日本語での設問]
**A:** [日本語での解答]

> **Evidence:** "[本文からの引用、<strong>動詞</strong>を太字に]"

- **構造分解:**
  <div class="syntax-panel syntax-panel-structure">
  <ul>
    <li><strong>主語 (S):</strong> [主語]</li>
    <li><strong>動詞 (V):</strong> [動詞]</li>
    <li><strong>目的語/補語:</strong> [O/C]</li>
  </ul>
  </div>
- **構文ポイント:**
  <div class="syntax-panel syntax-panel-point">[構文の解説]</div>

// 他の設問も同様の形式で...`
```

## 3. Implementation Steps

1.  **Update Data File**:
    *   Open appropriate data file (`grade3Data.js` or `gradePre2Data.js`)
    *   Add new entry with correct ID format
    *   Ensure all required fields are populated

2.  **Update `mockData.js`**:
    *   Import the data file if not already imported
    *   Add entry to `AVAILABLE_YEARS` array:
    ```javascript
    { id: "grade3-2025-2", year: 2025, session: 2, label: "2025年第2回 (Title)" }
    ```
    *   Ensure data is merged in `MOCK_DATA`:
    ```javascript
    export const MOCK_DATA = {
      ...GRADE3_DATA,
      ...PRE2_DATA
    };
    ```

## 4. Verification Checklist

- [ ] **Content**: Past and Original content display correctly
- [ ] **Questions**: All questions and answer keys visible
- [ ] **Translations**: Tooltip translations work on hover
- [ ] **Intent**: 作成意図・根拠 tab shows formatted content
- [ ] **Summary**: 本文要約 tab shows both past and original summaries
- [ ] **Comparison**: 過去問との比較 tab shows:
  - [ ] HTML table with borders (罫線)
  - [ ] トピックと展開の相違 section
  - [ ] 設問設計の比較 section (all questions Q26-Q30)
- [ ] **Syntax**: 構文解説 tab shows styled panels

## 5. Common Errors to Avoid

1.  **Markdown Tables**: Do NOT use `| --- |` format for comparison. Use HTML `<table class="comparison-table">`.
2.  **Missing Imports**: Ensure new data files are imported in `mockData.js`.
3.  **Missing AVAILABLE_YEARS Entry**: Data won't appear in dropdown without this.
4.  **Incomplete Comparison**: Must include both table AND additional sections (Topic Differences, Question Design).
5.  **Wrong CSS Classes**: Use exact class names: `comparison-section-header`, `syntax-panel`, `syntax-panel-structure`, `syntax-panel-point`.
