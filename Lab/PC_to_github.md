```
git init

# 新增檔案並提交
git add . 
git commit -m "初始提交"
```
- 在github建立倉庫
- 連結 GitHub 倉庫
```
git remote add origin <HTTP位置>
git branch -M main
git push -u --force origin main # 本地 `main` 分支與 GitHub `main` 分支關聯，並強制覆蓋遠端(⚠️ 慎用)
```