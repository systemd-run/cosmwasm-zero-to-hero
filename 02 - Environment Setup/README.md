# Part Two - Environment Setup

So you think you’re ready to start! Now we need to setup our development environment. First things first, text editors. I’ll rattle a few off for those that skipped ahead.

1. IntelliJ with Rust Plugin - [Setup Guide](https://www.youtube.com/watch?v=H_-L7sjLcH8)
1. VSCode - [Setup Guide](https://www.youtube.com/watch?v=aYsUBddY7KY)

The reason I'm not covering editor setup is that this would make the guide longer than it needed to be initially. I will simply provide pointers to help.

So we have our trusty text editor, it’s time for us to generate some boilerplate. Thankfully the guys at InterWasm have set this up for us! I’m assuming you have cargo and rust installed and ready to go!

## Ensuring Rustup is Installed

Firstly we're going to need to ensure rustup is setup. To do this run the following commands in your terminal:

```bash
rustup default stable
cargo version
# If version is lower than 1.55 we need to update by running:
rustup update stable
```

Credit to the guys at Interwasm for this, this snippet is taken from [here](https://docs.cosmwasm.com/docs/1.0/getting-started/installation#installing-rust-in-linux-and-mac).

## Adding the WASM Target

We need to build our smart contracts to WASM files. So we need to add the target for our builds. We do this by running these commands in your terminal

```bash
rustup target add wasm32-unknown-unknown
```

## Installing Cargo Generate

Another requirement we need to generate the boilerplate is Cargo Generate. This can be installed via CLI using commands:

```bash
cargo install cargo-generate --features vendored-openssl
cargo install cargo-run-script
```

## Generating CW-Template

Now we are ready to use [CW-Template](https://github.com/InterWasm/cw-template). Again credit to Interwasm.
CW-Template sets up a boilerplate contract project. It has two main ways to be used:

Using the latest version:

```bash
cargo generate --git https://github.com/CosmWasm/cw-template.git --name <PROJECT_NAME>
```

Using an older or a different branch:

```bash
cargo generate --git https://github.com/CosmWasm/cw-template.git --branch <BRANCH_NAME> --name <PROJECT_NAME>
```

For compatibility I am going to use an older version using the branch flag. This means if you are following along (you should be) we will be using the same package versions.

The version I will be using is `1.0-beta5`. So run the command:

```bash
cargo generate --git https://github.com/CosmWasm/cw-template.git --branch 1.0-beta5 --name cw-starter
```