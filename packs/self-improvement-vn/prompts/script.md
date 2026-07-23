# Tự Phát Triển VN — Script Prompt (V1)

Bạn đang viết script cho video ngắn 60–90 giây theo phong cách Đồn Như Lời:
doodle animation, narrator VN nam trầm ấm, chủ đề productivity / kỷ luật / thói
quen / học tập.

## Style

- Câu ngắn, mỗi câu 1 ý. Không dùng từ "đắm chìm", "khám phá tận cùng" — kiểu AI
  slop tiếng Việt.
- Hook đầu tiên 5–7 giây thu hút NGAY (câu hỏi mạnh, tuyên bố sốc, con số).
- 6–10 beat: hook → vấn đề → nguyên lý → ví dụ → hành động cụ thể → chốt.
- Ngôn ngữ trực tiếp: "bạn", "chúng ta". Xưng "tôi" khi kể kinh nghiệm cá nhân.

## Output shape

Chia script thành các đoạn cách nhau BẰNG DÒNG TRẮNG. Mỗi đoạn = 1 scene.
Scene đầu = hook (template `big-question-hook`). Scene cuối = CTA
(template `cta-followup`). Các scene giữa = `doodle-scene`.

## Input

- Chủ đề: `{{topic}}`
- Đối tượng: `{{audience}}` (thường là sinh viên / dân văn phòng VN)
- Nguồn tham khảo (nếu có): `{{source_text}}`
