# Website — https://dlhkaizen.github.io/aiagentreceipt/

Static GitHub Pages site: 4 pages × 7 languages (`/`, `/vi/`, `/zh-hans/`, `/pt-br/`, `/es/`, `/id/`, `/ja/`), light and
dark (prefers-color-scheme), responsive, no JavaScript, no external resource, no tracking. Generated — edit
`Scripts/web_copy.py` and run `python3 Scripts/build_publishing.py`, never the HTML.

Xem cục bộ: Claude preview `aiagentreceipt-website` (.claude/launch.json), hoặc
`python3 -m http.server 8716 --directory 13_APPS/016_AIAgentReceipt/PUBLISHING/Website` rồi mở http://localhost:8716/.

## Đẩy lên (Hồ làm — Claude KHÔNG push)

```bash
# Copy out of the factory repo first — a git repo nested inside 13_APPS would confuse the factory's own git.
rsync -a --exclude README.md 13_APPS/016_AIAgentReceipt/PUBLISHING/Website/ ~/Sites/aiagentreceipt/
cd ~/Sites/aiagentreceipt
git init -b main
git add .
git commit -m "AI Agent Receipt website 1.0"
git remote add origin git@github.com:dlhkaizen/aiagentreceipt.git   # tạo repo public "aiagentreceipt" trước trên GitHub
git push -u origin main
```

GitHub → repo → Settings → Pages → Source: *Deploy from a branch*, Branch `main` / `(root)`. `.nojekyll` đã có.
Chờ 1–2 phút rồi kiểm 4 URL trả 200 trước khi nộp App Store.
