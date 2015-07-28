# Introduction

As part of NPM support in BRJS we will provide a list of tools and best practices on how to develop projects in and with NPM. To make it easier for developers to use this tools we would like to provide them with a tool that makes it easy to do so in a way that doesn't require them to write a lot of boilerplate code or config.

One of the early decisions we made, was to use the NPM scripts as our build "tool". This will allow us to build projects in a standard and community approved way. It also reduces the barrier to entry, as developers familiar with NPM/Node will be able to understand and use our projects without having to know anything about Caplin.

An example of a standard way of developing NPM modules is to have a "build" and "test" NPM commands defined in the projects. This two commands allow a new developer to prepare a fresh project so it can be worked on, and it allows the developer to verify that everything still works. Many CI systems assume those commands to be available and run them by default on Node projects.

A typical project will therefore have many command scripts defined, and many of those commands will be the same across many projects we develop.

## Avoiding copy & paste

To avoid developers having to copy&paste a bunch of configuration into their projects and having to manually update them, we would like to create a tool that will make this easier for developers, avoid (too much) duplication, make it easy to follow company conventions whilst also providing the option for developers to easily try out new tools.

We will call this tool "uber" for now.

## Requirements

The tool should:

- maintain the standard way of building NPM modules (have npm `build`, `test` and `serve` commands for example)
- minimise the amount of boilerplate developers need to write
- take advantage of the full set of tools NPM provides (package.json config, ...)
- allow easy quick customisation of tools via command line arguments (which browsers to use for testing for example)
- allow developers to override commands with their own (don't want to use mocha for testing, that's perfectly fine for example)
- make it easy for projects to be updated when we change "uber"
