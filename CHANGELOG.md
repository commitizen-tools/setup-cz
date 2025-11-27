## v0.6.0 (2025-11-27)

### Feat

- **inputs**: Expose python-version param

## v0.5.2 (2025-11-25)

### Fix

- use pip as module

## v0.5.1 (2025-11-25)

### Fix

- use github-script which has more support than python shell

## v0.5.0 (2025-11-25)

### BREAKING CHANGE

- `cache` input is removed, as it's not adding any benefit
and increases complexity. `pip` deps are not being cached

### Fix

- remove unnecessary cache input

## v0.4.1 (2025-11-21)

### Fix

- **docs**: remove workaround on diagram

## v0.4.0 (2025-11-21)

### Feat

- **examples**: add a new more in-depth example

## v0.3.0 (2025-11-21)

### Feat

- **action**: add branding

### Fix

- **action**: 125 char description

## v0.2.1 (2025-11-21)

### Fix

- change cache description

## v0.2.0 (2025-11-21)

### Feat

- **action**: enable cache
- **examples**: add new build-changelog
- **examples**: add new collect-version-info

### Fix

- **tests**: add a new test for a command
- **example**: remove wrong parameter
- exclude nix from language profile

## v0.1.0 (2025-11-20)

### Feat

- **ci**: add bump action
- **ci**: introduce new setup-cz action

### Fix

- **bump**: remove wrong parameter
- **bump**: set correct action path in gh-actions-auto-docs
- point to the correct location of this action
- **test**: add a new more complex case to matrix
