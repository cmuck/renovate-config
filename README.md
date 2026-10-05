# Central Renovate Configuration

This repository contains the central, reusable [Renovate](https://docs.renovatebot.com/) configuration for projects maintained by `cmuck`. It provides a consistent baseline for dependency updates across repositories while keeping Renovate configuration in one place.

## Usage

Extend this preset from a repository's `renovate.json` or `renovate.json5` file:

```json
{
	"extends": ["github>cmuck/renovate-config:renovate.json5"]
}
```

Repository-specific settings can be added alongside `extends` and will be merged with this shared configuration. See Renovate's [shareable config presets](https://docs.renovatebot.com/config-presets/) for details.

## Included defaults

The current [configuration](./renovate.json5):

- extends Renovate's [`config:best-practices`](https://docs.renovatebot.com/presets-config/#configbest-practices) preset;
- enables automatic configuration migration;
- schedules lockfile maintenance for the first day of each month;
- waits 14 days after a release before proposing an update; and
- labels update pull requests with `dependencies`.

## Validation

Changes to the configuration are checked with Renovate's [configuration validator](https://docs.renovatebot.com/config-validation/) through [pre-commit](https://pre-commit.com/).

Install the hook and run it against all files:

```shell
pre-commit install
pre-commit run --all-files
```

The same check runs automatically in GitHub Actions for pull requests and changes pushed to `main`.

## License

This project is available under the terms of the [MIT License](./LICENSE).
