# Tự Phát Triển VN — Per-scene refine prompt (V1)

Với 1 đoạn narrator voice text, đề xuất các trường extra:

1. `emotion` — 1 trong: tired · motivated · frustrated · energetic · curious
2. `keyPoint` — 1 câu chốt ngắn (tối đa 8 từ) hiển thị màn hình. Bỏ trống nếu không có.

Input:
- `voiceText`: `{{voiceText}}`

Output STRICT JSON:
```json
{ "emotion": "…", "keyPoint": "…" }
```
