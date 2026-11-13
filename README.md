### patches

Collection of patches maintained by the **WF-DT-Sapphire** org.

Each `.patch` file in this repository fixes or adds a specific behavior in the org's builds/codebases. They are applied manually on top of the corresponding source tree.

### Contents

| Patch | Description | Target / Base |
|-------|-------------|---------------|
| `Trebuchet-Recents-lock-apps.patch` | _to be filled_ | `packages/apps/Trebuchet` |
| `disable-imeDrawsImeNavBar.patch` | _to be filled_ | `frameworks/base` |
| `microg.patch` | _to be filled_ | `frameworks/base` |
| `viperfx.patch` | _to be filled_ | `frameworks/base` |

> Fill in the **Description** column with 1–2 lines explaining what each patch does.

### How to apply

The examples below assume the patches are copied to `~/` and the tree is at `~/LOSMG`.

### viperfx

```bash
cd ~/LOSMG/frameworks/base
git apply --ignore-whitespace --check ~/viperfx.patch && \
  git apply --ignore-whitespace ~/viperfx.patch && \
  git status --short
```

### disable-imeDrawsImeNavBar

```bash
cd ~/LOSMG/frameworks/base && \
  git apply --check ~/disable-imeDrawsImeNavBar.patch && \
  git apply ~/disable-imeDrawsImeNavBar.patch && \
  git diff --stat
```

### microg

```bash
cd ~/LOSMG/frameworks/base && \
  git apply --check ~/microg.patch && \
  git apply ~/microg.patch && \
  git diff --stat
```

### Trebuchet-Recents-lock-apps

```bash
cd ~/LOSMG/packages/apps/Trebuchet && \
  git apply --check ~/Trebuchet-Recents-lock-apps.patch
```

To revert an already-applied patch, use `-R`:

```bash
cd ~/LOSMG/packages/apps/Trebuchet && \
  git apply --check -R ~/Trebuchet-Recents-lock-apps.patch
```

### Contributing

1. Generate the patch from a clean commit (`git format-patch` or `git diff > name.patch`).
2. Test with `git apply --check` against the target base.
3. Add an entry to the **Contents** table.
4. Open a PR describing the problem the patch solves.
