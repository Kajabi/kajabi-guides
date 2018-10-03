# RSpec Style Guide

This is a brand new work in progress.

## Syntax:

* Outer `describe` blocks should be prefixed with `RSpec` namespace, like `RSpec.describe`

## Capybara specs:

* Only include `js: true` flags on specifications and not groupings. Resist DRYing with groups
  to avoid using the javascript driver unnecessarily as the suite grows.
