# Usage

Here is an example to show how to run the code to train a logistic classifier on a simulated dataset, with no regularization, dropout (dropout rate = 0.1), L1 (weight = 10^0) or wMMD (weight = 10^3).

```shell
python main.py --num-vocabs 1000 --num-words 10 --sample-size 200 --embedding-size 5 --dist0-alpha 0.5
```
```shell
python main.py --num-vocabs 1000 --num-words 10 --sample-size 200 --embedding-size 5 --dist0-alpha 0.5 --structure dropout --dropout-rate 0.1
```
```shell
python main.py --num-vocabs 1000 --num-words 10 --sample-size 200 --embedding-size 5 --dist0-alpha 0.5 --regularization l1 --weight-exponent 0
```
```shell
python main.py --num-vocabs 1000 --num-words 10 --sample-size 200 --embedding-size 5 --dist0-alpha 0.5 --regularization wmmd --weight-exponent 3
```

To check more arguments of the commands, run
```shell
python main.py --help
```

# Simulation results

| $(n, V)$    | $\alpha_0 (\alpha_1 = 5.0)$ | No regularization | L1            | dropout       | wMMD (our)          |
|-------------|-----------------------------|-------------------|---------------|---------------|------------------------|
| (200, 500)  | $0.5$                       | 69.48 (1.251)     | 74.28 (1.102) | 74.14 (1.086) | **89.78 (0.483)** |
|             | $1.0$                       | 56.10 (0.772)     | 56.58 (0.757) | 58.26 (0.836) | **73.84 (0.746)** |
|             | $1.5$                       | 53.34 (0.764)     | 53.68 (0.772) | 55.02 (0.817) | **65.52 (0.794)** |
|             | $5.0$                       | 49.72 (0.749)     | 50.34 (0.732) | 50.88 (0.795) | 50.54 (0.541)          |
| (400, 500)  | $0.5$                       | 85.74 (0.901)     | 89.88 (0.420) | 90.67 (0.506) | **92.71 (0.279)** |
|             | $1.0$                       | 65.65 (0.770)     | 66.24 (0.837) | 68.58 (1.004) | **80.11 (0.414)** |
|             | $1.5$                       | 57.17 (0.731)     | 57.51 (0.693) | 58.67 (0.616) | **70.42 (0.509)** |
|             | $5.0$                       | 50.63 (0.513)     | 50.74 (0.542) | 50.38 (0.525) | 51.18 (0.538)          |
| (200, 1000) | $0.5$                       | 60.58 (0.939)     | 63.38 (1.169) | 61.96 (1.022) | **83.98 (0.615)** |
|             | $1.0$                       | 54.58 (0.659)     | 54.38 (0.671) | 54.76 (0.681) | **68.08 (0.683)** |
|             | $1.5$                       | 51.94 (0.841)     | 51.66 (0.821) | 53.16 (0.744) | **60.42 (0.740)** |
|             | $5.0$                       | 49.08 (0.695)     | 50.16 (0.751) | 50.52 (0.572) | 50.08 (0.706)          |
| (400, 1000) | $0.5$                       | 73.38 (1.131)     | 82.96 (0.555) | 77.94 (1.086) | **90.05 (0.331)** |
|             | $1.0$                       | 57.00 (0.773)     | 58.56 (0.692) | 59.20 (0.711) | **73.91 (0.430)** |
|             | $1.5$                       | 52.27 (0.564)     | 53.82 (0.547) | 53.78 (0.569) | **64.75 (0.592)** |
|             | $5.0$                       | 50.56 (0.470)     | 50.87 (0.513) | 50.53 (0.530) | 50.58 (0.469)          |
