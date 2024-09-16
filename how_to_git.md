To achieve this, you can configure your local Git repository to have two remotes: one for the original repository (to pull updates from) and one for your personal repository (to push your changes). Here's how you can set it up:

1. **Clone the original repository (if you haven’t already):**
   ```bash
   git clone https://github.com/original/repo.git
   ```

2. **Create your own repository on GitHub** and get the URL (e.g., `https://github.com/your-username/your-repo.git`).

3. **Check the current remote:**
   ```bash
   git remote -v
   ```
   You'll see something like:
   ```bash
   origin  https://github.com/original/repo.git (fetch)
   origin  https://github.com/original/repo.git (push)
   ```

4. **Add your personal GitHub repository as a new remote:**
   ```bash
   git remote add myrepo https://github.com/your-username/your-repo.git
   ```

5. **Push your local changes to your personal repository:**
   ```bash
   git push myrepo main  # or master, depending on your branch name
   ```

6. **To pull updates from the original repo** while still keeping your changes, you can pull from the `origin` remote:
   ```bash
   git pull origin main  # or master, depending on the branch
   ```

### Summary of remotes:
- **origin**: The original repository from where you cloned (you'll pull updates from here).
- **myrepo**: Your personal repository where you push your changes.

Now, you can push to your own repo with `git push myrepo`, and if the original repository gets updates, you can pull them using `git pull origin`.

If there are any conflicts while pulling from the original repo, Git will prompt you to resolve them before you can complete the pull.