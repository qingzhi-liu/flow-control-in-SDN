# flow-control-in-SDN

We make SDN networks based on Mininet emulator. Please install and setup miniet emulator from http://mininet.org/.

There are three source code files in this emulation. 
setup-mininet-opt.py
setup-mininet-eql.py
setup-dataprocess.py

setup-mininet-opt.py is for emulating the networking based on coFlow algorithm. 
setup-mininet-eql.py does not use coFlow algorithm, which is used as a benchmark networking. 
setup-dataprocess.py is used for final data processing. 
Refer to our paper for more detail about the parameters of the experiment setup. 

Please follow the steps below for running the emulation code. 
1. Change the file names of workload and bandwidth in setup-mininet-opt.py. For example, 
    workload_file = './settings/1/NEAL_V'
    bandwidth_file = './settings/1/NEAL_B'
NEAL_V is the file for setting the communication load between hosts.
NEAL_B is the file for setting the communication bandwidth between hosts.
2. Change the file name in setup-mininet-eql.py. For example, 
	bw_file = './settings/bw/bw_1_1_1'
bw_1_1_1 is the bandwidth of physical link between hosts and switch. 
3. Change the networking topology in the setupNetwork() function according to your own requirement. In this function, we use iperf3 to setup the commmunication load and bandwidth. 
4. The communication statistics results are written in txt files. We use independent txt file for each flow. For example, file "h1-s2.txt" has the result of flow from host2 to host1. 
5. Run setup-dataprocess.py to produce the final result. Please change the destination file name for outputting the result. For example, 
    result_file = "./results/1/Result_NEAL_C"
Result_NEAL_C is the name of the result file. 

