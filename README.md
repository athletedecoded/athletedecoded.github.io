# CV/Resume

## Developer Guide

This site is built using [Zola](https://www.getzola.org/) and Rust. This is a minimalist adaptation of the zola [resume theme](https://www.getzola.org/themes/resume/).

**Prereqs**

1. Install Rust + CC linker

    ```
    # Install Rust
    $ curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
    $ source "$HOME/.cargo/env"
    
    # Install CC linker
    $ sudo apt install build-essential
    ```

2. Ensure you have configured a Github SSH key [per the docs](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)


**Install Zola**

```
# Update rustup
$ rustup update stable

# Build Zola from Source
$ git clone https://github.com/getzola/zola.git
$ cd zola
$ cargo install --path . --locked

# Add Zola to $PATH
$ cp target/release/zola ~/.cargo/bin/zola

# Validate install
$ zola --version
```

**Serve Locally**

```
$ zola serve
```

**Deploy**

CI/CD deployment is automated with Github Actions.

`$git push origin main` triggers `./github/workflows/deploy.yml`

* Before 1st push: Settings > Actions > General > Workflow Permissions > Enable Read & Write permissions
* After 1st push: Settings > Pages > Build & Deployment > Select Branch: `gh-pages`
