# NEET


## Maze
### execution
```
$python run_maze.py
```
#### options:
| option          | default   | detail  |
| :---            | :---      | :---    |
| -n --name       | "{task}"  | experiment name |
| -t --task       | medium    | maze name (built on "envs/maze/maze_files/{name}.txt")) |
| -p --po-size    | 500       | population size of NEAT |
| --timestep      | 400       | timestep limit of solving maze |
| --num-cores     | 4         | number of parallel processes |
| --no-plot       | to plot   | not plot progress figure |


## Maze Hyper-NEAT
### execution
```
$python run_maze_hyper.py
```
#### options:
- -n --name         : experiment name (default: "{task}")
- -t --task         : task id (default: medium)
- -p --pop-size     : population size of neat (default: 500)
- -g --generation   : generations of neat (default: 500)
- --timesteps       : maze solving simulator steps (default: 400)
- --num-cores       : number of parallel processes (default: 4)
- --no-plot         : not plot progress figure


## Evogym
### execution
```
$python run_evogym.py
```
#### options:
- -n --name       : experiment name (default: "{task}_{robot}")
- -t --task       : task id (default: Walker-v0)
- -r --robot      : robot structure name (default: cat, built in "envs/evogym/robot_files/{name}.txt")
- -p --pop-size   : population size of neat (default: 200)
- -g --generation : generations of neat (default: 500)
- --eval-num      : if probabilistic task, need a certain times (default: 1)
- --num-cores     : number of parallel processes (default: 4)
- --no-view       : not view simulation of best robot

### make gif
after run_evogym, make gif file for each of all robots written in reward history file.
output to "./out/evogym_neat/{expt name}/gif/"
```
$python make_gifs.py -n {experiment name}
```
#### options:
- -n --name             : experiment name
- -r --resolution-ratio : image resolution ratio (default: 0.2 -> (256,144))
- -s --specified        : make gif for only specified robot (usage: "-s {id}")
- --num-cores           : number of parallel processes (default: 1)
- --not-overwrite       : skip process if already gif exists (default: overwrite)
- --no-multi            : do without using multiprocess. if error occur, try this option.


## Evogym Hyper-NEAT
### execution
```
$python run_evogym_hyper.py
```
#### options:
- -n --name       : experiment name (default: "{task}_{robot}")
- -t --task       : task id (default: Walker-v0)
- -r --robot      : robot structure name (default: cat, built in "envs/evogym/robot_files/{name}.txt")
- -p --pop-size   : population size of neat (default: 200)
- -g --generation : generations of neat (default: 500)
- --use-hidden    : make hidden nodes on NN substrate (default: False)
- --eval-num      : if probabilistic task, need a certain times (default: 1)
- --num-cores     : number of parallel processes (default: 4)
- --no-view       : not view simulation of best robot

### make gif
after run_evogym_hyper, make gif file for each of all robots written in reward history file.
output to "./out/evogym_hyper/{expt name}/gif/"
```
$python make_gifs_hyper.py -n {experiment name}
```
#### options:
- -n --name             : experiment name
- -r --resolution-ratio : image resolution ratio (default: 0.2 -> (256,144))
- -s --specified        : make gif for only specified robot (usage: "-s {id}")
- --num-cores           : number of parallel processes (default: 1)
- --not-overwrite       : skip process if already gif exists (default: overwrite)
- --no-multi            : do without using multiprocess. if error occur, try this option.


## Evogym Structure Evolution
### execution
```
$python run_evogym_cppn.py
```
#### options:
- -n --name       : experiment name (default: task id)
- -t --task       : task id (default: Walker-v0)
- --shape         : robot shape (usage: "--shape {height} {width}", default: (5,5))
- -p --pop-size   : population size of neat (default: 4)
- -g --generation : generations of neat (default: 500)
- --ppo-iters     : learning iterations of PPO algo (default: 5). on the more complex task, need more.
- --deterministic : evaluate robot on deterministic simulation (default: probabilistic)
- --num-cores     : number of parallel processes (default: 4)
- --no-view       : not view simulation of best robot

### make gif
after run_evogym_cppn, make gif file for each of all robots written in reward history file.
output to "./out/evogym_cppn/{expt name}/gif/"
```
$python make_gifs_cppn.py -n {experiment name}
```
#### options:
- -n --name             : experiment name
- -r --resolution-ratio : image resolution ratio (default: 0.2 -> (256,144))
- -s --specified        : make gif for only specified robot (usage: "-s {id}")
- --deterministic       : robot act deterministically (default: probabilistically)
- --num-cores           : number of parallel processes (default: 1)
- --not-overwrite       : skip process if already gif exists (default: overwrite)
- --no-multi            : do without using multiprocess. if error occur, try this option.