# Overall

| Optimization Target | CPUs | Replicas | Autotuner | Result Count | Reward |
|---------------------|------|----------|-----------|--------------|--------|
| Runtime             | 32   | 1        | nevergrad | 18           | 0.9709 |
| Runtime             | 32   | 5        | nevergrad | 89           | 1.0245 |
| Runtime             | 32   | 10       | nevergrad | 178          | 1.0357 |
| Runtime Series      | 32   | 1        | nevergrad | 18           | 0.8867 |
| Runtime Series      | 32   | 5        | nevergrad | 90           | 0.8690 |
| Runtime Series      | 32   | 10       | nevergrad | 177          | 0.8592 |


# Run 1: 32 CPUs, 1 replica, nevergrad autotuner

**Command (Runtime)**:

```
python -m llvm_autotuning.tune -m \
    experiment=my-exp \
    outputs=/tmp/logs \
    executor.cpus=32 \
    num_replicas=1 \
    autotuner=nevergrad \
    autotuner.optimization_target=runtime \
    autotuner.search_time_seconds=600
```

**Results**:

```
                                       num_benchmarks  num_results  walltime (s)  geomean_reward
experiment timestamp           config
my-exp     2022-07-19/16-51-50 C0                  18           18    616.932982         0.97094
```


**Command (Runtime Series)**:

```
python -m llvm_autotuning.tune -m \
    experiment=my-exp \
    outputs=/tmp/logs \
    executor.cpus=32 \
    num_replicas=1 \
    autotuner=nevergrad \
    autotuner.optimization_target=runtimeseries \
    autotuner.search_time_seconds=600
```

**Results**:

```
                                       num_benchmarks  num_results  walltime (s)  geomean_reward
experiment timestamp           config
my-exp     2022-07-19/16-33-38 C0                  18           18    638.704485        0.886655
```


# Run 2: 32 CPUs, 5 replicas, nevergrad autotuner

**Command (Runtime)**:

```
python -m llvm_autotuning.tune -m \
    experiment=my-exp \
    outputs=/tmp/logs \
    executor.cpus=32 \
    num_replicas=5 \
    autotuner=nevergrad \
    autotuner.optimization_target=runtime \
    autotuner.search_time_seconds=600
```

**Results**:

```
                                       num_benchmarks  num_results  walltime (s)  geomean_reward
experiment timestamp           config
my-exp     2022-07-26/12-30-50 C0                  18           89    661.248641        1.024497
```


**Command (Runtime Series)**:

```
python -m llvm_autotuning.tune -m \
    experiment=my-exp \
    outputs=/tmp/logs \
    executor.cpus=32 \
    num_replicas=5 \
    autotuner=nevergrad \
    autotuner.optimization_target=runtimeseries \
    autotuner.search_time_seconds=600
```

**Results**:

```
                                       num_benchmarks  num_results  walltime (s)  geomean_reward
experiment timestamp           config
my-exp     2022-07-26/11-46-36 C0                  18           90    690.013663        0.869043
```


# Run 3: 32 CPUs, 10 replicas, nevergrad autotuner

**Command (Runtime)**:

```
python -m llvm_autotuning.tune -m \
    experiment=my-exp \
    outputs=/tmp/logs \
    executor.cpus=32 \
    num_replicas=10 \
    autotuner=nevergrad \
    autotuner.optimization_target=runtime \
    autotuner.search_time_seconds=600
```

**Results**:

```
                                       num_benchmarks  num_results  walltime (s)  geomean_reward
experiment timestamp           config
my-exp     2022-07-28/12-26-30 C0                  18          178    658.266678        1.035727
```


**Command (Runtime Series)**:

```
python -m llvm_autotuning.tune -m \
    experiment=my-exp \
    outputs=/tmp/logs \
    executor.cpus=32 \
    num_replicas=10 \
    autotuner=nevergrad \
    autotuner.optimization_target=runtimeseries \
    autotuner.search_time_seconds=600
```

**Results**:

```
Aggregate over experiments:
                                       num_benchmarks  num_results  walltime (s)  geomean_reward
experiment timestamp           config
my-exp     2022-07-28/13-39-07 C0                  18          177    694.333734        0.859231
```
