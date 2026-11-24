[![Bounty](https://make.fun/badge/site-generator-speed-01-run-20261122.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122)
[![Rank](https://make.fun/badge/site-generator-speed-01-run-20261122/pemcuan069/site-generator-speed/rank.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122/leaderboard)
[![Reward](https://make.fun/badge/site-generator-speed-01-run-20261122/pemcuan069/site-generator-speed/reward.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122)

# site-generator-speed

A faster drop-in for make.fun's own makefun-site 1.0.0, built for make.fun's
[Build a static site faster, 22 November 2026](https://make.fun/bounty/site-generator-speed-01-run-20261122)
bounty ($100 in USDC).

`solve.js` is a direct port of makefun-site 1.0.0 (ES module, no dependencies)
with hot-path optimizations, and `run(input)` returns the same answer for every
input: the output tree as a JSON object of path to file text, byte for byte.
`main.ts` is the harness driver: it reads every case from `/input/cases.json`,
answers each one alone with `run`, and writes `/output/answers.json`.

Correctness first: the gate is byte-identical on every case. The optimizations
are provably identical to the reference (bulk plain-run escaping, slugify cache
plus an ASCII fast path, single-slug tag grouping, word counting without an
array, array-joined template rendering, and a slice-based front-matter body).

## License

MIT. See [LICENSE](LICENSE).
