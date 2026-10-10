# @tummycrypt/tinyland-metrics-collectors (retired)

> **Retired 2026-10-10.** This package was merged into
> [xoxd-ai/tinyland-otel](https://github.com/xoxd-ai/tinyland-otel) as the
> `./metrics-collectors` subpath export, shipped in `tummycrypt_tinyland_otel`
> 1.3.0 and later. This repository is archived and gets no further changes.

## Migration

- Bazel: remove `bazel_dep(name = "tummycrypt_tinyland_metrics_collectors", ...)`
  and depend on `bazel_dep(name = "tummycrypt_tinyland_otel", version = "1.3.0")`
  (or later) from [xoxd-ai/bazel-registry](https://github.com/xoxd-ai/bazel-registry).
- Imports: change `@tummycrypt/tinyland-metrics-collectors` to
  `@tummycrypt/tinyland-otel/metrics-collectors`. The API is the same
  (`configureMetricsCollectors`, `getMetricsCollectorsConfig`,
  `resetMetricsCollectorsConfig`, `collectProcessMetrics`,
  `collectSessionMetrics`, `collectAccessibilityMetrics`,
  `collectAuthMetrics`, `collectClientMetrics`, `collectAllMetrics`, and the
  types `MetricsWriter`, `AccessibilityMetricsData`,
  `MetricsCollectorsConfig`).
- The otel package root also re-exports the same names unchanged.

## Distribution

Bazel is the only distribution path for in-house packages. Nothing is published
to npm from this repository any more, and the publish workflow has been removed.
The Bazel module `tummycrypt_tinyland_metrics_collectors` (0.2.2, 0.2.3) is
marked deprecated in the registry but stays resolvable; nothing is yanked.
Earlier npm releases of `@tummycrypt/tinyland-metrics-collectors` remain on the
npm registry.

## What it was

Gauge collectors that write Node.js process metrics, file-backed session and
auth audit counts, accessibility issue counts and client placeholders to a
configurable `MetricsWriter`.
