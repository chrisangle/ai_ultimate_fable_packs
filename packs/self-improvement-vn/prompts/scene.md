# Tự Phát Triển VN — Per-scene refine prompt (V2, contract-aware)

Bạn là người tinh chỉnh scene cho kênh self-improvement / productivity tiếng Việt
(giống Đồn Như Lời). Pack ship 1 **catalog template** — bạn chọn ĐÚNG MỘT cho scene
này và điền slot inputs. Toàn bộ layout/art/motion do template quyết; bạn chỉ
lo TEXT và các field trạng thái nhân vật.

## Input

- `voiceText`: {{voiceText}}
- `sceneOrder`: {{order}} of {{total}}
- `previousTemplateId`: {{previousTemplateId}}
- `templateCatalog` (từ pack.json): {{templateCatalog}}

## Nhiệm vụ

1. **Pick `templateId`** từ `templateCatalog`:
   - `sceneOrder === 1` → PHẢI chọn entry có `role === "hook"` (`big-question-hook`).
   - `sceneOrder === total` → PHẢI chọn entry có `role === "outro"` (`cta-followup`).
   - Còn lại → `role === "body"` (`doodle-scene`).
2. **Fill `inputs`** — mọi slot REQUIRED, respect `maxLength`:
   - `big-question-hook`: `kicker` (nhãn đỏ ngắn, in hoa, ví dụ "BÍ MẬT", "SỰ THẬT") + `headline` (câu hỏi lớn 1 dòng, gây tò mò).
   - `doodle-scene`: `voiceText` = phiên bản gọn của input voiceText fit cho caption pill (≤180 ký tự, giữ nguyên nghĩa) + optional `footer` (nhãn dưới, mặc định "TỰ PHÁT TRIỂN").
   - `cta-followup`: `voiceText` (câu cảm ơn ngắn, ví dụ "Cảm ơn bạn đã xem.") + `cta` (nút chữ in hoa, ví dụ "THEO DÕI", "SUBSCRIBE").
3. **Fill `extraFields`** từ `pack.extraSceneFields`:
   - `emotion` — 1 trong: tired · motivated · frustrated · energetic · curious
   - `keyPoint` — 1 câu chốt ngắn (≤ 8 từ) hiển thị màn hình. Bỏ trống nếu không có.

## Quy tắc TTS tiếng Việt (BẮT BUỘC cho voiceText)

- Viết số ra chữ: `5.5` → `năm chấm năm`, `82.7%` → `tám mươi hai phẩy bảy phần trăm`, `iPhone 17` → `iPhone mười bảy`.
- Không dùng emoji/icon/URL trong voiceText.
- Câu kết `.` hoặc `?` để có ngắt nghỉ tự nhiên.

## Output — STRICT JSON, không thêm text

```json
{
  "templateId": "doodle-scene",
  "inputs": { "voiceText": "…", "footer": "TỰ PHÁT TRIỂN" },
  "extraFields": {
    "emotion": "…",
    "keyPoint": "…"
  }
}
```
