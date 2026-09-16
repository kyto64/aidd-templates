# AIDD template repositories

Development workspace for two GitHub template repositories, managed as **git submodules**.

| Submodule | Purpose | GitHub template |
|-----------|---------|-----------------|
| [aidd-template-lean/](./aidd-template-lean/) | Minimal AI-driven development template | `kyto64/aidd-template-lean` |
| [aidd-template-scale/](./aidd-template-scale/) | lean + VitePress, UI/E2E skills, lefthook, Dependabot | `kyto64/aidd-template-scale` |

**This parent repo is not a template.** Adopters should use **Use this template** on lean or scale directly.

## Clone

```bash
git clone --recurse-submodules git@github.com:kyto64/aidd-templates.git
# or
git clone --recurse-submodules https://github.com/kyto64/aidd-templates.git
```

If already cloned without submodules:

```bash
git submodule update --init --recursive
```

## Workflow

Work inside a submodule:

```bash
cd aidd-template-lean   # or aidd-template-scale
git status
gh ...
```

After pushing changes in a submodule, update the parent pointer:

```bash
cd /path/to/aidd-templates
git add aidd-template-lean aidd-template-scale
git commit -m "chore: bump submodule refs"
git push
```

## Regenerate scale from lean

```bash
cd aidd-template-scale
bash scripts/assemble-from-lean.sh ../aidd-template-lean
# commit and push in scale, then bump parent submodule ref
```

## GitHub templates

- lean and scale are **private template repositories** (`is_template: true`).
- Public visibility can be changed later per repository in GitHub Settings.
