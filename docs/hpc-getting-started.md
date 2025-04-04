## HPC Intro

The VSC (Vlaams Supercomputer Centrum) is a supercomputer center in Belgium that provides a high-performance computing (HPC) resources to researchers and institutions. It is a collaboration between several universities and research institutions in Flanders, Belgium.

They have a pretty good [documentation page](https://docs.vscentrum.be/) that is also opensource for everyone to contribute and improve.

It's slurm.

## HPC resources

To create detailed tables for each cluster profile and the resources and time allowed for each partition, we can follow the logic in the configuration. Here are the tables:

!!! info overhead
    A HPC needs a little memory for the operating system and other services. This is called overhead. The overhead is the memory that is not available for the user.  This is why the maximum memory available to the user is less than the total memory of the node.

Checking nodes:
```bash
sinfo
```
```bash
scontrol show node <node_name>
```

### [Genius Profile](https://docs.vscentrum.be/leuven/tier2_hardware/genius_hardware.html#hardware-details)

| Partition        | nCPUs | Max Memory | GPUs                     | Max Time |
| ---------------- | ----- | ---------- | ------------------------ | -------- |
| batch            | 36    | 180 GB     | -                        | 72 h     |
| batch_long       | 36    | 180 GB     | -                        | 168 h    |
| interactive      | 36    | 180 GB     | -                        | 72 h     |
| bigmem           | 36    | 703 GB     | -                        | 72 h     |
| bigmem_long      | 36    | 703 GB     | -                        | 168 h    |
| superdome        | 14    | 5772 GB    | -                        | 72 h     |
| superdome_long   | 14    | 5772 GB    | -                        | 168h     |
| gpu_p100         | 36    | 180 GB     | 4× NVIDIA P100 (16 GB)   | 72 h     |
| gpu_p100_long    | 36    | 180 GB     | 4× NVIDIA P100 (16 GB)   | 168 h    |
| gpu_p100_debug   | 36    | 180 GB     | 4× NVIDIA P100 (16 GB)   | 1 h      |
| gpu_v100         | 36    | 703 GB     | 8× NVIDIA V100 (32 GB)   | 72 h     |
| gpu_v100_long    | 36    | 703 GB     | 8× NVIDIA V100 (32 GB)   | 168 h    |
| amd              | 64    | 244 GB     | -                        | 72 h     |
| amd_long         | 64    | 244 GB     | -                        | 168 h    |

> - Numbers are for 1 node.
> - `amd` memories are not checked - will likely be less

### [Wice Profile](https://docs.vscentrum.be/leuven/tier2_hardware/wice_hardware.html#hardware-details)

| Partition               | nCPUs | Max Memory | GPUs                        | Max Time |
| ----------------------- | ----- | ---------- | --------------------------- | -------- |
| batch                   | 72    | 244 GB     | -                           | 72 h     |
| batch_long              | 72    | 244 GB     | -                           | 168 h    |
| bigmem                  | 72    | 2016 GB    | -                           | 72 h     |
| hugemem                 | 72    | 8 TB       | -                           | 72 h     |
| gpu                     | 72    | 512 GB     | 4× NVIDIA A100 (80 GB)      | 72 h     |
| gpu_a100                | 72    | 512 GB     | 4× NVIDIA A100 (80 GB)      | 72 h     |
| gpu_h100                | 64    | 703 GB     | 4× NVIDIA H100 (80 GB HBM3) | 72 h     |
| gpu_a100_debug          | 64    | 512 GB     | 1× NVIDIA A100 (80 GB)      | 1 h      |
| interactive             | 64    | 512 GB     | 1× NVIDIA A100 (80 GB)      | 72 h     |

> - Numbers are for 1 node. All nodes have 960 GB SSD local disk.
> - `hugemem` memories are not checked for overhead - will likely be less
> - `gpu` memories are not checked for overhead - will likely be less


