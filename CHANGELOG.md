# Changelog

## [11.0.0] - 2026-08-21

### Changed

- Package name: `electrik/teamwork` (fork of `mpociot/teamwork` 10.x).
- Require `illuminate/support|database|auth|contracts` `^10|^11|^12|^13` (Laravel 13 ready).
- Migration uses modern `id()` / `foreignId()` and a unique `(user_id, team_id)` index.
- Default `user_model` fallback is `App\Models\User`.

### Fixed

- Register `teamwork` as a container singleton (facade resolution).
- Typehint `Illuminate\Contracts\Foundation\Application` instead of the concrete Foundation app.
