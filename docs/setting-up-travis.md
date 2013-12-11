# Setting up Travis CI

Packages under the [atom org][atom-org] should use [Travis CI][travis-ci] for
builds.

Currently we have a [Travis Pro][travis-pro] account since the repositories
are private.  This process will be simpler and have fewer steps once the
package repos are made public.

Each package builds using the [build-package][build-package] script, any
changes to the build should be made in that script and will affect all
package builds immediately.

Each package builds against the latest successful build of atom@master. The
master builds are stored in the [atom-master-builds][atom-master-builds] repo
as releases named by the SHA-1 built.

## Configuring a package

* Run `cd ~/github/my-package` to navigate to the package repo locally
* Run `apm test` to verify that the package currently builds via [apm][apm]
* Add the package repo to the [Travis CI team][travis-ci-team]
* Run `gem install travis` to install the [travis gem][travis-gem]
* Run `travis login --pro` and log in using the [atom-build][atom-build] user
  and the password from the *Shared-Developers* folder in LastPass
* Run `apm ci` to add a `.travis.yml` file to the repo and to configure Travis
* Log into [Travis][travis-ci] as the `atom-build` user and you should now see
  the package listed and building
  

[apm]: https://github.com/atom/apm
[build-package]: https://github.com/atom/apm/blob/master/script/build-package
[atom-build]: https://github.com/atom-build
[atom-master-builds]: https://github.com/atom/atom-master-builds/releases
[atom-org]: https://github.com/atom
[travis-ci]: https://magnum.travis-ci.com
[travis-ci-team]: https://github.com/organizations/atom/teams/596636
[travis-gem]: https://rubygems.org/gems/travis
[travis-pro]: http://about.travis-ci.org/docs/user/travis-pro