# pccl

An independent reimplementation of PCCL, a collective-communication algorithm synthesizer for arbitrary topologies and concurrent process groups, described in [arXiv:2606.07019](https://arxiv.org/abs/2606.07019). The synthesized schedules are evaluated with [ASTRA-sim](https://github.com/astra-sim/astra-sim).

> This project is not affiliated with the paper's authors. Results may differ from those reported in the paper; deviations are documented below.

## Status

Work in progress.

## Requirements

- Python 3.12+ and [uv](https://docs.astral.sh/uv/)
- CMake, protobuf, and Boost (to build ASTRA-sim)

## Setup

```bash
git clone --recurse-submodules <repo-url>
cd pccl
uv sync
uv pip install -e third_party/astra-sim/extern/graph_frontend/chakra
```

Build the ASTRA-sim analytical backend:

```bash
PROTOBUF_FROM_SOURCE=True ./third_party/astra-sim/build/astra_analytical/build.sh
```

## Layout

```
src/pccl/       synthesizer: topology, collectives, routing, schedule, emitters
baselines/      reference algorithms (e.g. Direct All-to-All)
config/        topology and experiment definitions
experiments/    scripts that reproduce individual figures
tests/          schedule validation tests
third_party/    ASTRA-sim (pinned submodule)
```

## Deviations from the paper

None documented yet.
