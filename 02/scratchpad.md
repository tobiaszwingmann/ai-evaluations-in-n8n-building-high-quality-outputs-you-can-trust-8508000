# Chapter 2 Scratchpad

---

**Edit Fields**

- Name: `Evaluation`
- `chatInput` String: `{{ $json.question }}`
- `sessionId`String: `{{$now.toMillis()}}`
- Include Other Input Fields: `On`, `All`

---

**Switch**

```{{ $('Evaluation').item.json.id }}``` exists

---

**Edit Fields**
- Name: `Number of sources`
- `source_count` String:
```
{{
  ($json.output.split(/Sources:\s*\r?\n/)[1] || '')
    .split(/\r?\n/).length
}}
``` 

---

**Set Metrics**
- `Categorization`
- Expected Answer: `{{ $('Evaluation').item.json.expected_source_count }}`
- Actual Answer: `{{ $json.source_count }}`

Option:
- Metric name: `eval_source_count`
