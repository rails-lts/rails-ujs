# LTS

This is the LTS fork of rails-ujs.

## Supported jQuery versions

We test our patches against the following jQuery versions:

* 1.8.0
* 1.8.1
* 1.8.2
* 1.8.3
* 1.9.0
* 1.9.1
* 1.10.0
* 1.10.1
* 1.10.2
* 1.11.0
* 2.0.0
* 2.1.0

## Running tests

```
# Runs all Qunit tests in all versions in chrome with capybara
$script/run_tests

# Runs Qunit tests for 1.8.0 & 1.8.1
$VERSIONS=1.8.0,1.8.1 script/run_tests

# Runs suite with :selenium-chrome
$NO_HEADLESS=1 script/run_tests
```

## Releasing a patch

Rails-LTS does not publish this gem or npm package in any repository. Rails-LTS customers point directly to this repository and the branch `lts` in their app's Gemfile.
Make sure to add your patch to the correct `lts` branch. Doublecheck that your patch includes a newly built dist version.

1. `git checkout lts`
2. `git checkout -b lts-patch-cve-1234`
3. Add your fix
4. Run `script/run_tests`
5. Run `bundle exec blade build`
6. Open up a PR against `lts`
7. Review and merge
