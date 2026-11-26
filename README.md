# micrograd-value-graph

A minimal Python `Value` class implementing computation graphs and Graphviz visualization (`trace` and `draw_dot`), built while learning *micrograd*-style autograd from scratch.

## Features
- `Value` class tracking numerical `.data`, parent dependencies (`_prev`), and operation labels (`_op`) for `+` and `*`.
- `trace(root)` to collect all reachable `Value` nodes and directed edges.
- `draw_dot(root)` to render a left-to-right Graphviz (`Digraph`) computation graph.

## Requirements
- Python 3
- `graphviz` (Python package + system Graphviz binary)
- `numpy` and `matplotlib` (for numerical sampling and plotting experiments)

## Example
```python
from graphviz import Digraph

a = Value(2.0)
b = Value(-3.0)
c = Value(10.0)
d = a * b + c

dot = draw_dot(d)
dot
