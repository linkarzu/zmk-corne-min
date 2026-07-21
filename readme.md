
# Corne Mini ZMK Config

## Useful video

<!-- markdownlint-disable -->
<!-- prettier-ignore-start -->
 
<!-- tip=green, info=blue, warning=yellow, danger=red -->
 
> [!TIP]
> I go over how to do all this [in this YouTube video in my Channel](https://youtu.be/qm6ds3Bc8Zc?si=NFzz_8H1qyXkz9pR)
 
<!-- prettier-ignore-end -->
<!-- markdownlint-restore -->

I recently did another review of the keyboard, around 11 days after using it
daily, video can be found here:
[The Corne Min Prototype Is Beautiful… But It Hurts](https://youtu.be/1jUPrg9d6-g)

## Repo info

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

## 7. Flash firmware for the first time

The first time you need to flash the firmware, it will not come with a
bootloader key, so you need to enter bootloader mode with the pins that are on
the back of each half

Take a look at this image
[provided in discord](https://discord.com/channels/336826782772756481/1402261105484501045/1524092108779294730)

![Image](./readme-img/260708-123305.avif)

After you connect the USB you will see the keyboard on your computer.

When you see the keyboard on your computer you can let go of the boot pins

For the left half I dragged `corne_min_left_with_studio.uf2`

After you drag the file to the left half and you're done, disconnect it, and
follow the same steps with the right half

For the right half I dragged `corne_min_right.uf2`

## 8. Configure bootloader buttons and flash the firmware that way

Take a look at my keymap file, you'll see the `&bootloader` key I use to put
each half on bootloader mode

It doesn't matter if you keep each halve on or off, I'll turn them off just in
case:

1. Turn off left half
2. Connect USB cable
3. Press `&bootloader` key
4. Keyboard appears, drag the file
5. Disconnect half
6. Do the same for the other half

