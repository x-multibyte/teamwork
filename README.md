# Electrik Teamwork

Fork of [mpociot/teamwork](https://github.com/mpociot/teamwork) maintained for **Electrik**.

## Why this fork exists

Upstream `mpociot/teamwork` `^10` only allows Laravel 9–12. Electrik targets current Laravel (including **13**) and Livewire 4. This fork:

- Declares support for Laravel **10–13** via `illuminate/*` constraints
- Keeps the `Mpociot\Teamwork` namespace (drop-in API)
- Registers a proper `teamwork` container singleton
- Modernizes the default migration (`id()` / `foreignId()`, unique membership)

Livewire is not a dependency of Teamwork; Electrik’s Livewire UI sits on top of this package.

## Install

```bash
composer require electrik/teamwork
```

Until Packagist is published, path/VCS install from this repo:

```json
{
  "repositories": [
    {
      "type": "path",
      "url": "../teamwork",
      "options": { "symlink": true }
    }
  ],
  "require": {
    "electrik/teamwork": "@dev"
  }
}
```

Then:

```bash
php artisan vendor:publish --provider="Mpociot\Teamwork\TeamworkServiceProvider"
php artisan migrate
```

Add `Mpociot\Teamwork\Traits\UserHasTeams` to your User model and set `teamwork.team_model` to your Team class (Electrik uses `Electrik\Models\Team`).

## License

MIT — same as upstream Teamwork.
