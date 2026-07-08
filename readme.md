
# Corne Mini ZMK Config

This repo is a fork of the MechboardsUK ZMK config for the Corne Mini.

```text
Original repo: https://github.com/MechboardsLTD/zmk-config
Fork: https://github.com/linkarzu/zmk-corne-min
Git branch: corne-min
Keymap file: config/corne_min.keymap
```

## 1. Fork the Mechboards repo

Open the original repo:

```text
https://github.com/MechboardsLTD/zmk-config
```

Select the branch:

```text
corne-min
```

Click:

```text
Fork
```

Name the fork:

```text
zmk-corne-min
```

The fork should be:

```text
https://github.com/linkarzu/zmk-corne-min
```

## 2. If the fork only has `main`

Look at the branches that your fork has on GitHub, sometimes GitHub only copies
the default branch. So let's get the `corne-min` branch

Clone your fork:

```bash
mkdir -p ~/github
cd ~/github

git clone git@github.com:linkarzu/zmk-corne-min.git
cd zmk-corne-min
```

Add the original repo as `upstream`:

```bash
git remote add upstream https://github.com/MechboardsLTD/zmk-config.git
git fetch upstream
```

Create the local `corne-min` branch from upstream:

```bash
git switch -c corne-min upstream/corne-min
```

Push `corne-min` to your fork:

```bash
git push -u origin corne-min
```

## 3. Set `corne-min` as the default branch

Open your fork on the GitHub website:

```text
https://github.com/linkarzu/zmk-corne-min
```

Go to:

```text
Settings → Branches
```

Change the default branch to:

```text
corne-min
```

## 4. Use the repo locally

Go to the repo:

```bash
cd ~/github/zmk-corne-min
```

Switch to the correct branch (I do the steps from here in Lazygit)

```bash
git switch corne-min
git pull
```

Confirm the branch:

```bash
git branch
```

Expected:

```text
* corne-min
  main
```

## 5. Edit the keymap

The keymap file is:

```text
config/corne_min.keymap
```

Edit it, commit, and push:

```bash
git add config/corne_min.keymap
git commit -m "Update Corne Mini keymap"
git push
```

## 6. Build firmware

After pushing, open the fork:

```text
https://github.com/linkarzu/zmk-corne-min
```

Go to:

```text
Actions
```

Open the latest successful build and download the firmware artifact ZIP.

