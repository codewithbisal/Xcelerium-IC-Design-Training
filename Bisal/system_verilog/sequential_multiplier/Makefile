# Define variables
TOP_MODULE = tb_Top_Module
SRC_DIR = src
SRC_FILES = $(SRC_DIR)/datapath.sv $(SRC_DIR)/control.sv $(SRC_DIR)/top.sv $(SRC_DIR)/tb_Top_Module.sv
WORK_DIR = work

# Default target
all: compile simulate

# Create a working library and compile source files
compile:
	@echo "Creating work library..."
	vlib $(WORK_DIR)
	@echo "Compiling source files..."
	vlog -work $(WORK_DIR) $(SRC_FILES)

# Run the simulation
simulate:
	@echo "Running simulation..."
	vsim -c -do "run -all; quit" -L $(WORK_DIR) $(TOP_MODULE)

# Clean up generated files
clean:
	@echo "Cleaning up..."
	rm -rf $(WORK_DIR) transcript vsim.wlf

.PHONY: all compile simulate clean