# PLI - Prolog Libraries Index

PLI aims to be an index (and maybe in the future a package manager) for prolog libraries.

In my option a (new) prolog implemention should be as slim as possibile and include external libaries.

## WHY

- The most famous and used programming languages have a package manager where developers can find easily useful libraries and do not have to "reinvent the wheel".
- There are several prolog implementations with their own set of libraries. Probably a subset of then could be shared among the implementations.
- There are only package managers and repositories for specific prolog implementations (ex. packs  https://www.swi-prolog.org/pack/list for swi-prolog).

## ISSUES

- Libraries are distribuited in several SCM repositories or web sites without any naming convention about folders and files.
- Some libraries work only for a specific prolog implementation
- A library could be a set of files inside a folder (inside a git repository) or a single .pl file

## DESIDERATA

I'd like to have an index where I could find a list of prolog libraries with some metadata/info like
- name and short description
- which prolog implementations / release are supported
- license
- dependencies

I'd like to have also a tool for downloading the libraries and include them in my project. In details:
- a library should be installed inside the project folder and not at system level
- the developer should be able to rename the libraries inside his/her project to avoid conflicts.

## PROPOSAL

The index could be a git repository with only the metadata/info of the libraries like "melpa" for emacs.

The packages could be saved in a subfolder of the project like

	packs/atom_feed_lib/atom_feed.pl
	packs/twitter_client/prolog/login.pl
	packs/twitter_client/prolog/tweets.pl

With swi-prolog we could use then with

	asserta(user:file_search_path(library, 'packs')
	use_module(library(atom_feed_lib/atom_feed)).
