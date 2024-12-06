# Advent of Code Elixir Starter

Template repository for Elixir solutions to [Advent of Code][aoc] puzzles.

Adapted from another [Advent of Code Elixir Starter][aoc-starter].

## ✨ Features ✨
- Four Mix tasks: (Run `mix help <task_name>` after building the project for usage info)
  - `mix advent.gen` - Generate boilerplate solution and test modules for a new year of puzzles.
  - `mix advent.solve` - Run or benchmark a solution.
  - `mix advent.test` - Run tests against a solution. (A convenience wrapping `mix test`)
  - `mix advent.try` - Run tests followed by a solution. (A convenience wrapping `mix advent.test` and `mix advent.solve`)
- Automatically downloads puzzle inputs as needed.
- Optional benchmarking with Benchee.
- [Special support][shared-parse] for puzzle solutions that reuse the same parsed value for both parts.
- [Optionally run in a container that handles Erlang/Elixir installation for you.](#get-started-in-a-self-contained-environment)

## Usage

Start by creating your own repository from this template, using the big green
button up there ↗️.

Once that's done, let's get your project running.

Enable the automatic puzzle input downloader by creating a `config/secrets.exs`
file containing the following:

```elixir
import Config

config :advent_of_code, AdventOfCode.Input,
  allow_network?: true,
  session_cookie: "..." # paste your AoC session cookie value here
```

Fetch dependencies with
```shell
mix deps.get
```

Generate a set of solution and test files for a new year of puzzles with
```shell
mix advent.gen -y${YEAR}
```

Now you can run a solution with
```shell
mix advent.solve -d${DAY} [-p${1 | 2}] [-y${YEAR}] [--bench]
```

and tests with
```shell
mix advent.test [-d${DAY}] [-y${YEAR}]
```

either directly in your local terminal, or in VSCode's terminal pane while
connected to a dev container as described below.

As an additional convenience, you can also use
```shell
mix advent.try -d${DAY} [-p${1 | 2}] [-y${YEAR}] [--bench]
```
to run tests, and then if they pass, a solution.

## Get started in a self-contained environment

<img width="1912" alt="Screenshot of the project running in GitHub Codespaces" src="https://github.com/user-attachments/assets/8b2e5625-c9dc-489b-99a3-39b7a8888c00">

Your project generated from this template repository can optionally run in a dev container for remote development.\
You have two options:

### :octocat: Run in your browser using GitHub Codespaces

1. Go to the landing page of your generated repo.
1. Click the `<> Code` drop-down menu, select the Codespaces tab, and click the
   big green button.
1. Wait for the Codespace to build.[^1]
1. Once the in-browser editor activates, follow the steps from [Usage](#usage)
   to enable puzzle downloads and run a solution. (You can use
   <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>`</kbd> to open a terminal pane.)

### :whale: Using Visual Studio Code + Docker Desktop

Requires Docker Desktop or an alternative Docker-compliant CLI, like podman.

Simply open the project directory locally in VS Code. It will show a popup
asking if you want to use the Dev Container. It will then guide you through
getting set up, building the container image, and connecting to the running dev
container.

[^1]: If you decide to stick with Codespaces, consider [configuring prebuilds][prebuilds-docs]
      for your project to speed up build time.

[aoc]: https://adventofcode.com/
[aoc-starter]: https://github.com/mhanberg/advent-of-code-elixir-starter
[shared-parse]: lib/advent_of_code/solution/shared_parse.ex
[prebuilds-docs]: https://docs.github.com/en/codespaces/prebuilding-your-codespaces/configuring-prebuilds
