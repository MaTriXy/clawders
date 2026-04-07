# 📝 CLAUDE.md

Project-specific instructions for Claude Code agents.

---

## Large File Handling

When reading large files, run `wc -l` first to check the line count.

If a file exceeds **2000 lines**, use the `offset` and `limit` parameters on the `read_file` tool to read the file in chunks rather than attempting to read the entire file at once.

**Example approach:**

```
First read:  offset=0,  limit=500   (lines 1-500)
Second read: offset=500, limit=500  (lines 501-1000)
Third read:  offset=1000, limit=500  (lines 1001-1500)
... and so on
```

This keeps memory usage manageable and prevents the model from getting lost in huge files.
