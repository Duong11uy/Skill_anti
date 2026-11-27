# Personal Dev & RE Toolkit (Antigravity Plugin)

Gói plugin cá nhân tổng hợp từ **4 repository**:
1. [`morluto/rea`](https://github.com/morluto/rea) — Skill `reverse-engineer-anything` + cấu hình MCP `rea`
2. [`dietrichgebert/ponytail`](https://github.com/dietrichgebert/ponytail) — 6 skills viết code tối giản (`ponytail*`) + rule
3. [`obra/superpowers`](https://github.com/obra/superpowers) — 15 skills quy trình kỹ thuật (brainstorming, TDD, planning, debugging, subagent...) + rule
4. [`github/spec-kit`](https://github.com/github/spec-kit) — 9 skills Spec-Driven Development (`speckit-*`)

## Cấu trúc thư mục

- `plugin.json`: Khai báo gói plugin cho Antigravity nhận diện tự động.
- `skills/` (**34 skills**): Toàn bộ kỹ năng từ 4 repo trên + 3 lệnh tắt `/rea`, `/speckit`, `/superpowers`.
- `rules/AGENTS.md`: Các quy tắc hành xử luôn bật (gồm rule cá nhân + rule của `ponytail` và `superpowers`).
- `mcp_config.json`: Khai báo MCP server `rea` để skill `reverse-engineer-anything` có tool chạy phân tích binary/JS/APK.

## Cách gọi lệnh chủ động (Slash Commands) & Tự động kích hoạt

Trong Antigravity, **mọi skill đều hỗ trợ cả 2 chế độ**:
- **Tự động:** Nếu bạn không gõ lệnh `/`, AI vẫn tự đọc mô tả skill (và `rules/AGENTS.md`) để tự kích hoạt skill phù hợp khi thấy cần.
- **Chủ động gọi bằng `/`:**
  - `/ponytail`, `/ponytail-review`, `/ponytail-audit`, `/ponytail-debt`, `/ponytail-gain`, `/ponytail-help`
  - `/rea` (lệnh tắt cho `/reverse-engineer-anything`)
  - `/speckit` (điểm vào chung) hoặc gọi thẳng `/speckit-constitution`, `/speckit-specify`, `/speckit-clarify`, `/speckit-plan`, `/speckit-checklist`, `/speckit-tasks`, `/speckit-analyze`, `/speckit-implement`, `/speckit-converge`
  - `/superpowers` (điểm vào chung) hoặc gọi thẳng `/brainstorming`, `/writing-plans`, `/executing-plans`, `/test-driven-development`, `/systematic-debugging`, `/verification-before-completion`, v.v.

## 1. Đẩy lên Git repository (từ máy hiện tại)

```powershell
cd "C:\Users\TOPV.LAPTOP.144\.gemini\antigravity\scratch\personal-toolkit"
git init
git add .
git commit -m "Bundle rea, ponytail, superpowers, and spec-kit into personal plugin"
git branch -M main
git remote add origin https://github.com/Duong11uy/Skill_anti.git
git push -u origin main
```

## 2. Cài đặt trên máy mới (1 lệnh)

### Windows (PowerShell)

```powershell
git clone https://github.com/Duong11uy/Skill_anti.git "$HOME\.gemini\config\plugins\personal-toolkit"
```

### macOS / Linux

```bash
git clone https://github.com/Duong11uy/Skill_anti.git ~/.gemini/config/plugins/personal-toolkit
```

Sau khi clone, **khởi động lại Antigravity**. Để cập nhật trên mọi máy:

```powershell
git -C "$HOME\.gemini\config\plugins\personal-toolkit" pull
```

## 3. Yêu cầu runtime trên máy mới

- **Cho `rea` (`reverse-engineer-anything`):** Cần Node.js `22.x (>=22.23.4)`, `24.x (>=24.22.1)` hoặc `>=26.12.1` kèm `npm`.
- **Cho `spec-kit` (`speckit-*`):** Trong từng dự án mới muốn dùng Spec-Driven Development, khởi tạo thư mục `.specify/` bằng:
  ```powershell
  uv tool install specify-cli
  specify init --here --integration agy --script py
  ```
- **Tránh trùng lặp:** Trên máy nào đã cài riêng plugin `ponytail`, `superpowers` hoặc cấu hình `rea` trong `~/.gemini/config/mcp_config.json`, nên tắt/gỡ bản cài rời trước khi bật `personal-toolkit` để tránh trùng lặp.
