# What is sha-miner?
This project was created to understand how cryto-currency miners work. For a while, I have understood at a high-level what miners do but the best way for me to really understand was to implement it myself.

# How does the project work 
I read the source code for [geth](https://github.com/ethereum/go-ethereum) to understand how `difficulty` is implemented and how `hashrate` was computed. This example miner uses all of your CPU cores "mine" a nonce which is below the threshold. 

# Usage 

```
$ sha-miner -h
Usage of sha-miner:
  -d, --difficulty uint   Difficulty value to use for mining (default 100000000)
  -m, --message string    Message to compute the hash (default "Hello world.")
  -t, --threads int       Total number of threads to use. Defaults to number of CPUs (default 1)
```

# Installation 
For the latest binaries, download them [here](https://github.com/amir20/sha-miner/releases).

# Installation from source
You need to have `pflags` and `go-metrics`. You can install them by doing 

```
go get -u github.com/rcrowley/go-metrics
go get -u github.com/spf13/pflag
```

[Goreleaser](https://goreleaser.com/#fpm_linux_packages) is used to build binaries for all operating systems. You need to have `rpmbuild` and `fpm` installed. You can do so by doing `brew install rpm` and follow the installation instruction for [fpm](http://fpm.readthedocs.io/en/latest/installing.html).

# Example Output

```
$ sha-miner -m "This is sample data"
Effective Hashrate is 0.00 MH/s
Effective Hashrate is 5.87 MH/s
Effective Hashrate is 5.81 MH/s
Effective Hashrate is 5.81 MH/s
Found nonce 11529215046083745388 with hashrate of 5.77 MH/s
```