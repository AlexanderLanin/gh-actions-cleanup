# gh-actions-cleanup

Cleanup old GitHub Actions runs.

The cleanup cutoff is sent to GitHub as a server-side `created` filter. This
means a repository's newest 1,000 runs cannot hide older runs that are eligible
for cleanup.

```sh
./gh-actions-cleanup --days 30 --dry-run
./gh-actions-cleanup --days 30
```

GitHub returns at most 1,000 results for a filtered workflow-run query. If more
than `--limit` runs match the cutoff, run the command again after each cleanup,
or narrow the cleanup window with a larger `--days` value.
