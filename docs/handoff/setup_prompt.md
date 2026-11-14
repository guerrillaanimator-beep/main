# PC の Claude Code に送る、Git とファイルの準備の依頼文

Sengoku Run のフォルダ（.uproject がある場所）で Claude Code を開き、下の文を貼り付けて送る。
GitHub のリポジトリ名を `sengoku-run` 以外にした場合は、6 の URL を書き換える。

---

このフォルダ（UE 5.8.4 の C++ プロジェクト「Sengoku Run」）を Git で管理できるようにして、作業用のファイルを入れてください。C++ の実装はまだ始めないでください。

1. **確認**：git と git lfs が入っているか確認してください。入っていなければ、入れ方を教えてそこで止まってください。
2. **作業用ファイルを取ってくる**：`https://github.com/guerrillaanimator-beep/main.git` の `claude/sakurai-skill-register-qt7jws` ブランチを、このフォルダの**外**の一時フォルダに clone してください。そこから次のファイルをコピーします。
   - `docs/handoff/CLAUDE.md` → このフォルダ直下の `CLAUDE.md`
   - `docs/spec_core.md` → `docs/spec_core.md`
   - `docs/handoff/ue.gitignore` → `.gitignore`
   - `docs/handoff/ue.gitattributes` → `.gitattributes`

   コピーが終わったら、一時フォルダは消してください。
3. **sakurai スキル**：`https://github.com/kociden/sakurai-skill.git` を一時フォルダに clone して、`skills/sakurai` をユーザーのスキルフォルダ（`~/.claude/skills/sakurai`）にコピーしてください。このプロジェクトの中には入れません。コピーする前に `SKILL.md` を読んで、ゲーム制作の原則のテキストだけであることを確かめてください。終わったら一時フォルダは消してください。
4. **Git の初期化**：ブランチ名 `main` で `git init` し、`git lfs install` してください。次の2つを確かめてください。
   - `Binaries/`、`Intermediate/`、`Saved/`、`DerivedDataCache/` が無視されている
   - `.uasset` と `.umap` が LFS の対象になっている
5. **最初のコミット**：コミットする前に、追加されるファイルの数と合計サイズを見せてください。LFS の対象外で 50MB を超えるファイルがあれば、止まって相談してください。問題なければ、全部追加してコミットしてください。
6. **GitHub に上げる**：リモートに `https://github.com/guerrillaanimator-beep/sengoku-run.git` を登録して、`main` を push してください。
7. **報告**：`CLAUDE.md` と `docs/spec_core.md` があること、push できたことを報告して止まってください。
