
# Git Merge vs Rebase 

## 🔀 What is Merge?
**Merge = Combine two branches without changing history.**

Git keeps all commits and adds **one new merge commit**.

### Example
You have:
- `main` branch  
- `feature` branch (your new code)

Command:
```bash
git checkout main
git merge feature
````

### Before merge

```
A — B — C — D (main)
        \
         E — F (feature)
```

### After merge

```
A — B — C — D — M
        \       /
         E — F
```

`M` = merge commit.

### When to use merge

* You want safe, original history.
* You want to see clearly when branches split and joined.

---

## 🔁 What is Rebase?

**Rebase = Move your branch to start from a new base (rewriting history).**

Git “replays” your commits on top of the latest commit.

### Example

Command:

```bash
git checkout feature
git rebase main
```

### Before rebase

```
A — B — C — D (main)
        \
         E — F (feature)
```

### After rebase

```
A — B — C — D — E' — F'  (feature)
```

Your commits (E', F') look new but content is same.

### When to use rebase

* You want a clean, straight history.
* You want your branch to look like it started from the latest main.
* Mostly used before merging a feature branch.

---

## 🥶 Merge vs Rebase — Quick Comparison

| Feature      | Merge                    | Rebase                   |
| ------------ | ------------------------ | ------------------------ |
| History      | Keeps full history       | Rewrites history         |
| Merge commit | Yes                      | No                       |
| Visual       | Tree-like                | Straight line            |
| Safety       | Safe for shared branches | Avoid on shared branches |
| Use case     | Team projects            | Cleaning up history      |

---

## 🧠 Real-life analogy

* **Merge:** Combine two story versions and add a note saying “merged both.”
* **Rebase:** Rewrite your story part as if you started after your friend’s latest version.

---

```

If you want I can also give a **short .md version**, **cheat sheet**, or **diagrams only Markdown**.
```
