# Graph Report - scratch-2026-11-16-8a78d8  (2026-11-16)

## Corpus Check
- Corpus is ~3,170 words - fits in a single context window. You may not need a graph.

## Summary
- 26 nodes · 42 edges · 6 communities (4 shown, 2 thin omitted)
- Extraction: 95% EXTRACTED · 5% INFERRED · 0% AMBIGUOUS · INFERRED: 2 edges (avg confidence: 0.9)
- Token cost: 85,224 input · 0 output

## Community Hubs (Navigation)
- Lưu dữ liệu & xử lý lỗi
- Kết nối & đồng bộ
- Hiển thị lịch tháng
- Tính tiền lương
- Trạng thái ứng dụng
- Trang & bảng chấm công

## God Nodes (most connected - your core abstractions)
1. `connect()` - 10 edges
2. `render()` - 9 edges
3. `store (putEntry, delEntry, putSettings)` - 8 edges
4. `useLocal()` - 5 edges
5. `fillForm()` - 5 edges
6. `writeErr()` - 4 edges
7. `entryForm submit handler (validate and save day entry)` - 4 edges
8. `payOf()` - 3 edges
9. `local (localStorage so-luong-v1)` - 3 edges
10. `readForm()` - 3 edges

## Surprising Connections (you probably didn't know these)
- `connect()` --implements--> `Shared DB with localStorage fallback storage pattern`  [INFERRED]
  so-luong.html → so-luong.html  _Bridges community 1 → community 0_
- `Sổ Lương Cá Nhân (personal payroll page)` --calls--> `connect()`  [EXTRACTED]
  so-luong.html → so-luong.html  _Bridges community 5 → community 1_
- `render()` --shares_data_with--> `state (entries, settings, month, selected, mode)`  [EXTRACTED]
  so-luong.html → so-luong.html  _Bridges community 4 → community 2_
- `render()` --calls--> `payOf()`  [EXTRACTED]
  so-luong.html → so-luong.html  _Bridges community 3 → community 2_
- `store (putEntry, delEntry, putSettings)` --calls--> `local (localStorage so-luong-v1)`  [EXTRACTED]
  so-luong.html → so-luong.html  _Bridges community 4 → community 0_

## Import Cycles
- None detected.

## Hyperedges (group relationships)
- **Persistence flow: shared DB or localStorage** — so_luong_connect, so_luong_uselocal, so_luong_store, so_luong_local, so_luong_entries_collection, so_luong_config_main [EXTRACTED 0.95]
- **User write actions with shared error handling** — so_luong_entryform_submit, so_luong_delyes_handler, so_luong_savesettings_handler, so_luong_writeerr [EXTRACTED 0.95]

## Communities (6 total, 2 thin omitted)

### Community 0 - "Lưu dữ liệu & xử lý lỗi"
Cohesion: 0.31
Nodes (8): db doc 'config/main', delYes handler (confirmed delete), db collection 'entries', entryForm submit handler (validate and save day entry), saveSettings handler, store (putEntry, delEntry, putSettings), toast(), writeErr()

### Community 1 - "Kết nối & đồng bộ"
Cohesion: 0.50
Nodes (4): connect(), setStatus(), useLocal(), window.claude.use (db/user runtime capabilities)

### Community 2 - "Hiển thị lịch tháng"
Cohesion: 0.67
Nodes (3): fillForm(), render(), shiftMonth()

### Community 3 - "Tính tiền lương"
Cohesion: 0.67
Nodes (3): payOf(), readForm(), updatePreview()

## Knowledge Gaps
- **1 isolated node(s):** `window.claude.use (db/user runtime capabilities)`
  These have ≤1 connection - possible missing edges. (Counts symbols only; 3 node(s) total have ≤1 connection when file, concept and rationale nodes are included.)
- **2 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `render()` connect `Hiển thị lịch tháng` to `Lưu dữ liệu & xử lý lỗi`, `Kết nối & đồng bộ`, `Tính tiền lương`, `Trạng thái ứng dụng`, `Trang & bảng chấm công`?**
  _High betweenness centrality (0.388) - this node is a cross-community bridge._
- **What connects `window.claude.use (db/user runtime capabilities)` to the rest of the system?**
  _1 weakly-connected nodes found - possible missing edges._
- **Why does `store (putEntry, delEntry, putSettings)` connect `Lưu dữ liệu & xử lý lỗi` to `Hiển thị lịch tháng`, `Trạng thái ứng dụng`?**
  _High betweenness centrality (0.365) - this node is a cross-community bridge._
- **Why does `connect()` connect `Kết nối & đồng bộ` to `Lưu dữ liệu & xử lý lỗi`, `Hiển thị lịch tháng`, `Trang & bảng chấm công`?**
  _High betweenness centrality (0.323) - this node is a cross-community bridge._