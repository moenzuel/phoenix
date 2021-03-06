# Release Instructions

**IMPORTANT**: when building the archive, it must be done in the minimum supported Erlang and Elixir versions.

  1. Check related deps for required version bumps and compatibility (`phoenix_ecto`, `phoenix_pubsub_redis`, `phoenix_html`)
  2. Bump version in related files below
  3. Update `phoenix_dep` in `installer/lib/phoenix_new.ex` and `installer/lib/phx_new/generator.ex` to "~> version to be released"
  4. Run tests, commit, push code
  5. Publish packages and docs after pruning any extraneous uncommitted files
  6. Run `MIX_ENV=prod mix archive.build` and `MIX_ENV=prod mix archive.build -o phx_new.ez` inside "installer" directory to build new installers
  7. Copy new installers to "phoenixframework/archives" project
  8. Test installer by generating a new app, running `mix deps.get`, and compiling
  9. Start -dev version in related files below
  10. Update `phoenix_dep` in `installer/lib/phoenix_new.ex` back to git
  11. Publish to `npm` with `npm publish`
  12. Replace `master` for `source_url_pattern` in `installer/mix.exs`
  13. Push installer (phx_new hex package) to hex

## Files with version

  * `CHANGELOG`
  * `mix.exs`
  * `installer/mix.exs`
  * `installer/README.md`
  * `package.json`
  * `assets/package.json`
  * `guides/introduction/installation.md`
