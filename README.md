## Octotree
Browser extensions (Chrome, Firefox, Safari and Opera) to display GitHub code in tree format. Useful for developers who frequently read source in GitHub and do not want to download or checkout too many repositories. Features:

* Easy-to-navigate code tree like IDEs
* Fast browsing with pjax
* Customizable hotkey
* Support private repositories (see [instructions](#github-access-token))
* Support GitHub Enterprise (Chrome and Opera only, see [instructions](#github-enterprise))

## Install on Chrome and Firefox
* Download and install Octotree from [Chrome Web Store](https://chrome.google.com/webstore/detail/octotree/bkhaagjahfmjljalopjnoealnfndnagc) or [Mozilla Add-ons Store](https://addons.mozilla.org/en-US/firefox/addon/octotree/)
* Navigate to any GitHub repository (or just refresh this page as an example)
* The code tree should show on the left-hand side of the screen

## Install on Safari and Opera
You can install the prebuilt extensions located in the [dist](https://github.com/buunguyen/octotree/tree/master/dist) folder. For security reason, only download Octotree from this location.

* Safari: drag `safari.safariextz` to the browser and follow the instructions
* Opera: drag `opera.nex` to the browser and follow the instructions

## GitHub access token
Octotree uses [GitHub API](https://developer.github.com/v3/) to retrieve repository metadata. By default, it makes unauthenticated requests to the GitHub API. However, there are two situations when requests must be authenticated:

* You access a private repository
* You exceed the [rate limit of unauthenticated requests](https://developer.github.com/v3/#rate-limiting)

When that happens, Octotree will ask for your [GitHub personal access token](https://help.github.com/articles/creating-an-access-token-for-command-line-use). If you don't already have one, [create one](https://github.com/settings/tokens/new), then copy and paste it into the textbox. Note that the minimal scopes that should be granted are `public_repo` and `repo` (if you need access to private repositories).

Alternatively, you can manually enter or update the token by following these steps:

* Navigate to any GitHub repository
* Open the Chrome (or Safari, Firefox) developer console
* Execute the following line:
```javascript
localStorage.setItem('octotree.github_access_token', 'REPLACE WITH TOKEN')
```

Note: if you use GitHub Enterprise, each site will need its own access token. Therefore, Octotree stores access token on a per-site basis.


## GitHub Enterprise
By default, Octotree only works on `github.com`. To support GitHub Enterprise on Chrome or Opera, you must grant Octotoree sufficient permissions. Follow these steps to do so:

* Navigate to any GitHub repository on `github.com`
* Open Octotree's setting panel
* Fill in the GitHub Enterprise URLs textbox, one site URL per line
* Click Save and accept any permission prompt
* Navigate to your GitHub Enterprise site (or refresh if you're already in one)
* You might be asked to create an [access token](#github-access-token)


## Changelog
### [v1.4](https://github.com/buunguyen/octotree/issues?labels=&milestone=4&page=1&state=closed)
* Support GitHub enterprise
* Change default hotkey (`cmd+b` for Safari and `cmd+shift+s` for all other browsers)
* Some other minor changes

### [v1.3](https://github.com/buunguyen/octotree/issues?labels=&milestone=3&page=1&state=closed)
* Setting panel allowing:
 * Changing access token
 * Changing hotkeys
 * Changing sidebar default visibility
 * Changing folder collapsing option
* Sidebar appears better in large monitors
* More responsive in big repositories
* And bug fixes

### [v1.2](https://github.com/buunguyen/octotree/issues?labels=&milestone=1&page=1&state=closed)
* Hide sidebar by default (upon many user requests)
* Hotkey (`cmd+b`, `ctrl+b`) to toggle sidebar
* Sidebar is now resizable
* Support rendering submodules
* Reflect GitHub selection to Octotree
* New sidebar header and progress indicator
* And bug fixes

### [v1.1](https://github.com/buunguyen/octotree/issues?labels=&milestone=2&page=1&state=closed)
* New UI that blends better with GitHub!
* Hide Octotree on non-code pages
* When asking for token, show more detailed message and not fly out automatically
* Extend pjax timeout to work better with big files
* Sanitize file and folder names before displaying
* Fix error when a branch name contains slashes
* Gulp script to build for Chrome, Firefox and Safari
* And some other minor changes

## Support Octotree
Octotree started out as a weekend project to [scratch my own itch](https://news.ycombinator.com/item?id=7740226). Since then, I have spent a lot of time adding features, fixing bugs and handling pull requests. If you find Octotree useful or want to support its development, please consider [donating a small amount](https://www.paypal.com/cgi-bin/webscr?cmd=_xclick&business=buunguyen@gmail.com&currency_code=USD&amount=&return=https://github.com/buunguyen/octotree&item_name=Support+Octotree).

## Credit
* Many thanks to all contributors who submit pull requests, report bugs and suggest ideas
* [Extension icon](https://github.com/pstadler/octofolders) by [pstadler](https://github.com/pstadler)