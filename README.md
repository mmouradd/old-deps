# old-deps-test

Synthetic uv project for testing a dependency-upgrade tool's resolution/latency.
All dependencies below are pinned to deliberately old versions (spanning 2020-2021 releases).

## ⚠️ No uv.lock included — why

This project was generated in a sandboxed environment with no PyPI network access,
so `uv lock` could not actually resolve/hash these packages here. Shipping a
hand-written "lock file" would mean fake hashes and fake resolved metadata,
which would be worse than no lock file for testing a real upgrade tool.

To generate the real lock file, run this once on a machine with internet access:

    cd old-deps-test
    uv lock

That will produce a genuine `uv.lock` resolving all 25 pinned deps below, which
you can then feed into your upgrade tool.

## Regenerating / re-pinning
If you want a different old-version mix, just edit the version pins in
`pyproject.toml` and re-run `uv lock`.
