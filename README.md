# blog-style-ghostwriter

A Codex skill for turning fragmented notes into Jekyll-compatible technical blog posts in an existing structured engineering-blog style.

The repository itself is the skill root, so you can clone it directly into a Codex skills directory or copy this folder as-is.

## Files

- `SKILL.md`: skill instructions and drafting workflow
- `agents/openai.yaml`: UI metadata
- `references/style-profile.md`: distilled style guide from existing blog posts
- `requirements-dev.txt`: minimal validation dependency

## Local Validation

```bash
python3 -m venv .venv
.venv/bin/python -m pip install -r requirements-dev.txt
.venv/bin/python /path/to/quick_validate.py .
```

`quick_validate.py` is provided by the Codex `skill-creator` system skill. Replace `/path/to/quick_validate.py` with the validator path on your machine.

## Example Usage

```text
Use $blog-style-ghostwriter to turn these scattered notes into a publish-ready post for my blog.
```
