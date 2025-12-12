
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



# Git Branching Strategies

## 1. Why Branching?
Branches allow developers to work on features, fixes, and releases without affecting the stable production code.

---

## 2. Common Branches
- **main/master** → Stable production-ready code  
- **dev/develop** → Integration/testing branch  
- **feature/** → New feature development  
- **release/** → Final prep before production  
- **hotfix/** → Urgent production fixes  

---

## 3. How Code Moves from DEV → PROD
1. Create a **feature branch**  
2. Complete work → Merge into **dev**  
3. After testing → Merge **dev → release**  
4. After QA → Merge **release → main**  
5. Hotfix flows → **hotfix → main + dev**

---

## 4. Branching Strategies

---

### A. Git Flow (Classic / Waterfall Style)
Uses:
- **master**
- **develop**
- **feature/**
- **release/**
- **hotfix/**

**Flow:**  
feature → develop → release → master  
hotfix → master + develop

**Pros:** Structured, stable  
**Cons:** Slow for fast releases  

**Best for:** Large teams, long release cycles

---

### B. Feature Branching (Agile / DevOps)
Uses:
- **main**
- **feature/**

**Flow:**  
feature → main (via Pull Request)

**Pros:** Simple, clean history  
**Cons:** Requires strong CI/testing  

**Best for:** Agile teams, microservices

---

### C. Trunk-Based Development (TBD)
Uses:
- **main** + very short-lived branches

**Flow:**  
Small commits → Merge to main frequently  
Uses **feature flags** for incomplete features

**Pros:** Very fast, fewer merge conflicts  
**Cons:** Needs discipline + automation  

**Best for:** High-speed DevOps, CI/CD

---

## 5. Long-Lived vs Short-Lived Branches

### Long-Lived Branches
- **main/master**
- **develop** (in Git Flow)

### Short-Lived Branches
- **feature**
- **release**
- **hotfix**

---
