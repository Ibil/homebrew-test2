- [Intro](#intro)
- [FAQS:](#faqs)
  - [If you need to uninstall yarn:](#if-you-need-to-uninstall-yarn)
  - [Naming your formulae to avoid clashes](#naming-your-formulae-to-avoid-clashes)
  - [Adding formulas](#adding-formulas)
  - [updates](#updates)
# Intro
This repo was created in order for everyone at appletv to get the same versions of the setup dependencys.

By using brew and naming this repo with the "homebrew-" prefix, the brew commmand can now install dependencys from this repo.
More info: https://docs.brew.sh/How-to-Create-and-Maintain-a-Tap

ex:
githubrepo name: homebrew-examplerepo
githuh repo owner: exampleuser
example formula name: yarnd.rb

brew install exampleuser/examplerepo/yarnd


# FAQS:

## If you need to uninstall yarn:

brew uninstall yarn

which yarn // lists directories where yarn is installed. should be none
// if some are listed, you can check [this in order to uninstall yarn from the pc](https://stackoverflow.com/questions/42334978/how-do-i-uninstall-yarn)


## Naming your formulae to avoid clashes
If your formulae have the same name as Homebrew/homebrew-core formulae they cannot be installed side-by-side. If you wish to create a different version of a formula that’s in Homebrew/homebrew-core (e.g. with options) consider giving it a different name e.g. nginx-full for more fully-featured nginx formula. This will allow both nginx and nginx-full to be installed at the same time (assuming one is keg_only or the linked files do not clash).

[Versioned formula example](https://github.com/Homebrew/homebrew-core/blob/master/Formula/node%4014.rb)

## Adding formulas
Tap formulae follow the same format as the homebrew core’s ones, and can be added under either the Formula subdirectory, the HomebrewFormula subdirectory or the repository’s root. The first available directory is used, other locations will be ignored. We recommend use of subdirectories because it makes the repository organisation easier to grasp, and top-level files are not mixed with formulae.

See [homebrew/core](https://github.com/Homebrew/homebrew-core) for an example of a tap with a Formula subdirectory.


## updates
simply make a pr and once merged run `brew upgrade`
