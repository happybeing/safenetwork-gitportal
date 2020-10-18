# Decentralised GUI for git on Safe Network

**STATUS:** under discussion - comments and contributions are welcome

# Safe-git UI - Vision
The direction is to provide a github like web UI which runs locally and provides a decenralised github like experience based on Safe Network storage. Safe Network is a secure, anonymous, decentralised storage and applications platform (see [safenetwork.tech](https://safenetwork.tech)).

<img src="./diagrams/past-and-future.png" alt="contrasting git with github and git with Safe architectures">

## github/gitlab/gitea like GUI
Possibly a Tauri based Rust backend with web frontend, e.g. using Svelte:
* operates on a local repo:
	* spawns git commands
	* a new `gitex` CLI to create issues, comments etc (e.g. stored in  ``.gitex``)
	* data for extas held in the repo (e.g. ``issues.json`` and ``issues/issue-001.json``, or perhaps in RDF/turtle)
* `git push/pull` remotes on Safe (e.g. via FUSE mounted Safe filesyste)
* cross platform GUI: Windows, MacOS and Linux (e.g. using [Tauri](https://tauri.studio))
* cross platform terminal UI: Windows, MacOS and Linux (e.g. using [tui-rs](https://github.com/fdehau/tui-rs))
* web UI for mobile (e.g. static HTML hosted on Safe Network)

# Discussions to Have

## Existing git UIs
There are many graphical, web and terminal UIs for `git`, so these may be adapted or learned from. 

Which should we look at and why? If you know any well your input would be very helpful.

## gitex requirements
`gitex` is a new CLI we need to create that adds features not handled by git, such as github issues.

- `gitex` based features must work in a way which allows a GUI to support them by spawning `git` and `gitex` commands. Doing so enables anyone to operate using the CLI, or to build their own Safe-git UI with the tools of their choice.

- where `gitex` adds something based on a github feature, it should also provide a way to import this from a github repo using the github APIs.

- what features do we want, and what difficulties do they present?

- How to store and publish `gitex` extras?
  Note that Safe has a built in perpetual history for public data which negates the need for `.gitex` to be under `git`. But then we need a way for third parties to create issues in a way that makes them accessible to everyone interested in a git repository published on Safe.

## Development Tools
I'm keen to try out Tauri and Svelte at least for proof of concept, but if we define the underlying data storage and structures for `gitex`, anyone will be able to build a GUI with the tools of their choice (e.g. spawning `git` and `gitex` commands).

So feel free to build your own Safe-git UI tools.

## How To Discuss

You can open an issue to discuss something specific or join the more general discussion on the Safe Network forum topic: [Safe-git UI Discussion](https://safenetforum.org/t/safe-git-ui-discussion/32793?u=happybeing)

# Contributions

Pull requests to enhance or add to this list are welcome but are accepted on the condition that they are licenced according to same terms as the LICENSE for software and other resources in this repository.

# LICENSE

SAFE Network Farming resources herein are licensed under GPLv3 (for details see [./LICENSE](./LICENSE))
