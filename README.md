Manual
Prerequisites
a. NS-3 Installation: Ensure NS-3 (version 3.35 or a compatible version) is installed on your system. The latest version can be downloaded from the official NS-3 website, along with installation instructions.
b. Environment Setup:
•	Place all necessary experiment files (such as aodv_m_test.cc) and the manet.csv file containing node positions in the scratch directory within your NS-3 installation.

•	Verify that the manet.csv file is correctly formatted, containing columns for node IDs, x-coordinates, and y-coordinates to ensure proper positioning of nodes in the simulation.
Experiment Files
•	Simulation File: aodv_m_test.cc - This is the main source code file for the AODV protocol simulation.

•	Node Position File: manet.csv - A CSV file that specifies X-Y coordinates for each node in the network.
Steps to Run the Experiment
a. Navigate to NS-3 Directory: Open a terminal and navigate to the root directory of your NS-3 installation.
b. Place Files in the Scratch Directory: Ensure both aodv_m_test.cc and manet.csv are in the scratch directory for easy access by the simulator.
c. Build the Simulation File: Compile and run the simulation code by entering the following command:
          ./waf build --run scratch/aodv_m_test
•	If the build completes successfully, the simulation will automatically start.

•	In case of any errors, check for missing dependencies or syntax issues within the code.
d. Configure Command-Line Parameters: Optional parameters for the simulation can be adjusted directly in the command line, as shown below:
./waf --run "scratch/aodv_m_test --size=100 --transmissionRange=50 --time=10"

•	Available Parameters:
o	--size: Specifies the number of nodes (default is 100).
o	--transmissionRange: Sets the transmission range in meters (default is 50).
o	--time: Defines the total simulation time in seconds (default is 10).
e. Output Files: Upon completion, the simulation generates several output files:
•	PCAP Traces (if enabled): Stored as aodv-xx.pcap files for packet capture analysis.

•	NetAnim File: aodv_simulation.xml, which can be used for network visualization in NetAnim.

•	Flow Monitor XML: flow-monitor-results.xml, containing detailed flow statistics.


•	CSV Results: results.csv, which includes metrics like Packet Delivery Ratio (PDR), average throughput, and end-to-end delay.

f. Analysed Results: After the simulation ends, open the results.csv file to review key performance metrics. This file provides a summary of PDR, throughput, and delay, enabling you to analyse the AODV protocol's effectiveness.

g. Run Simulation with Varying Parameters:
Vary Node Count:
o	Place simul.py in the NS-3.35 directory, then run the following command:
                       python3 simul.py
o	This generates a file named results.csv with results from varying node counts. Rename it to results_by_varying_nodes.csv for clarity and future reference.
Vary Transmission Range:
o	Place simul1.py in the NS-3.35 directory, then run it with:
                 python3 simul1.py
o	This creates transmission_range_results.csv, containing data from simulations with different transmission ranges.
h. Generate Graphs:
•	To create visualizations for Node Count vs. PDR, Node Count vs. Average Throughput, and Node Count vs. End-to-End Delay, run the ns3_results_1.py script.

•	For graphs depicting Transmission Range vs. PDR, Transmission Range vs. Average Throughput, and Transmission Range vs. End-to-End Delay, use the ns3_results_2.py script.

![image](https://github.com/user-attachments/assets/d5b7bc58-9aa3-4a12-9586-4d4d2a7a9771)
