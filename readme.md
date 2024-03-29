- [Intro](#intro)
- [updating formula versions](#updating-formula-versions)
- [FAQS:](#faqs)
  - [Naming your formulae to avoid clashes](#naming-your-formulae-to-avoid-clashes)
  - [Adding formulas](#adding-formulas)
  - [If you need to uninstall yarn:](#if-you-need-to-uninstall-yarn)

# Intro
This repo was created in order for everyone at appletv to get the same versions of the setup dependencys.

By using brew and naming this repo with the "homebrew-" prefix, the brew commmand can now install dependencys from this repo.
More info: https://docs.brew.sh/How-to-Create-and-Maintain-a-Tap

## example of setup:

### settings
```
githubrepo name: homebrew-examplerepo
githuh repo owner: exampleuser
example formula name: yarnd.rb
```

### tap install command
``
brew install exampleusername/examplereponame/yarnd
``

# updating formula versions

To change a formula verssion, open it's file and change these entries:

```
  desc "JavaScript package manager"
  homepage "https://yarnpkg.com/"
  url "https://yarnpkg.com/downloads/1.22.19/yarn-v1.22.19.tar.gz"
  sha256 "732620bac8b1690d507274f025f3c6cfdc3627a84d9642e38a07452cc00e0f2e"
  license "BSD-2-Clause"
```

Then, simply make a pr and once merged each user must run `brew upgrade`

# FAQS:

## Naming your formulae to avoid clashes
If your formulae have the same name as Homebrew/homebrew-core formulae they cannot be installed side-by-side. If you wish to create a different version of a formula that’s in Homebrew/homebrew-core (e.g. with options) consider giving it a different name e.g. nginx-full for more fully-featured nginx formula. This will allow both nginx and nginx-full to be installed at the same time (assuming one is keg_only or the linked files do not clash).

Use only lower-case characters for fomula file names

[Versioned formula example](https://github.com/Homebrew/homebrew-core/blob/master/Formula/node%4014.rb)

## Adding formulas
Tap formulae follow the same format as the homebrew core’s ones, and can be added under either the Formula subdirectory, the HomebrewFormula subdirectory or the repository’s root. The first available directory is used, other locations will be ignored. We recommend use of subdirectories because it makes the repository organisation easier to grasp, and top-level files are not mixed with formulae.

See [homebrew/core](https://github.com/Homebrew/homebrew-core) for an example of a tap with a Formula subdirectory.

## If you need to uninstall yarn:

``
brew uninstall yarn
``

Verify if yarn was unninstalled with the following command. It lists directories where yarn is installed. There should be none.

``
which yarn 
``

If some are listed, you can check [this in order to uninstall yarn from your device](https://stackoverflow.com/questions/42334978/how-do-i-uninstall-yarn)



