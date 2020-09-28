# <orb-name> Orb [![CircleCI Build Status](https://circleci.com/gh/<org-name>/<repo-name>.svg?style=shield "CircleCI Build Status")](https://circleci.com/gh/<org-name>/<repo-name>) [![CircleCI Orb Version](https://img.shields.io/badge/endpoint.svg?url=https://badges.circleci.io/orb/<orb-namespace>/<orb-name>)](https://circleci.com/orbs/registry/orb/<orb-namespace>/<orb-name>) [![GitHub License](https://img.shields.io/badge/license-MIT-lightgrey.svg)](https://raw.githubusercontent.com/<org-name>/<repo-name>/master/LICENSE) [![CircleCI Community](https://img.shields.io/badge/community-CircleCI%20Discuss-343434.svg)](https://discuss.circleci.com/c/ecosystem/orbs)

This CircleCI Orb helps continuously integrating replikativ projects

## Usage

Example use-cases are provided on the orb [registry page](https://circleci.com/orbs/registry/orb/replikativ/clj-tools#usage-examples). Source for these examples can be found within the `src/examples` directory. Unittests are run via `./bin/run-unittests` and integration tests are run via `./bin/run-integrationtests`. Formatting is done via `clojure -Sdeps '{:deps {cljfmt/cljfmt {:mvn/version "0.7.0"}}}' -m cljfmt.main check`, a build is executed with `seancorfield/depstar` and deployments to Clojars are done `deps-deploy/deps-deploy`.

For using the default replikativ workflow it is only necessary to basically copy one of the examples into the `.circleci/config.yml` file, commit and push it. The default steps are setup, format, build, unittest, deploy-snapshot (for commits to development branch) and deploy-release (for commit to master branch). If you want to run integration tests there is one already there for integrationtesting with a PostgreSQL database that listens on port 5432 with a database 'config-test', user 'alice' and password 'foo'. One for PostgreSQL and MariaDB exists as well, connection to MariaDB works quite the same.
