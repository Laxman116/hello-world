# Test against the latest version of this Node.js version
environment:
  nodejs_version: "6"

# Install scripts. (runs after repo cloning)
install:
  # Get the latest stable version of Node.js or io.js
  - ps: Install-Product node $env:nodejs_version
  # install modules
  - npm install

# Post-install test scripts.
test_script:
  # Output useful info for debugging.
  - node --version
  - npm --version
  # run tests
  - npm test

# Don't actually build.
build: off

