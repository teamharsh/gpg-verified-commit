# Setup Guide for Signing Git Commits with GPG on Windows

In this guide, you will learn how to configure your Windows machine to sign your Git commits using GPG keys. Signed commits are marked as verified on GitHub, ensuring that your changes come from a trusted source.

## Table of Contents

1. [Introduction to Signed Commits](#introduction-to-signed-commits)
2. [Verified Commits vs Unverified Commits on GitHub](#verified-commits-vs-unverified-commits-on-github)
3. [Download and Install GPG4WIN](#download-and-install-gpg4win)
4. [Generate GPG Key and Configure GitHub](#generate-gpg-key-and-configure-github)
5. [Configure Git to Sign Commits](#configure-git-to-sign-commits)
6. [Create Signed Commits](#create-signed-commits)
7. [Thank You](#thank-you)

## Introduction to Signed Commits

This video tutorial will guide you through the process of configuring your Windows machine to sign your Git commits using GPG keys.

## Verified Commits vs Unverified Commits on GitHub

Learn about the difference between verified and unverified commits on GitHub and why it is important to sign your commits.

## Download and Install GPG4WIN

1. Download the GPG4WIN software from [GPG4WIN](https://www.gpg4win.org/).
2. Follow the installation instructions to install GPG4WIN on your Windows machine.

## Generate GPG Key and Configure GitHub

1. Open a terminal and generate a GPG key:
    ```sh
    gpg --full-generate-key
    ```
2. List your GPG keys with their key IDs:
    ```sh
    gpg --list-secret-keys --keyid-format LONG
    ```
    Look for the line that starts with `sec` and note your key ID (`YOUR-KEY-ID`).

3. Export your public key:
    ```sh
    gpg --armor --export YOUR-KEY-ID
    ```

4. Add your GPG key to your GitHub account:
    - Copy the output of the export command.
    - Go to GitHub and navigate to **Settings > SSH and GPG keys**.
    - Click **New GPG key**, paste your key, and save it.

## Configure Git to Sign Commits

1. Set your Git username and email:
    ```sh
    git config --global user.name "YOUR-NAME"
    git config --global user.email "YOUR-EMAIL"
    ```

2. Configure Git to use your GPG key for signing commits:
    ```sh
    git config --global user.signingkey YOUR-KEY-ID
    git config --global commit.gpgsign true
    git config --global tag.gpgsign true
    git config --global gpg.program "C:\Program Files (x86)\GnuPG\bin\gpg.exe"
    ```

3. Verify your Git configuration:
    ```sh
    git config --global --list
    ```

## Create Signed Commits

Now you can create signed commits using Git. When you commit changes, Git will use your GPG key to sign the commits, and they will be marked as verified on GitHub.

## Thank You

Thank you for watching this video and following this guide. Signed commits help ensure the integrity and authenticity of your contributions. 🚀