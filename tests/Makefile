SIM ?= icarus 
WAVES ?= 1
TOPLEVEL_LANG ?= verilog
VERILOG_SOURCES += $(PWD)/../hdl/or_gate.v

VERILOG_SOURCES += $(PWD)/../hdl/dut.v
VERILOG_SOURCES += $(PWD)/wrappers/dut_test.v

VERILOG_SOURCES += $(PWD)/wrappers/or_test.v
VERILOG_SOURCES += $(PWD)/wrappers/ifc_test.v
VERILOG_SOURCES += $(PWD)/../hdl/ifc_or.v
VERILOG_SOURCES += $(PWD)/../hdl/FIFO1.v
VERILOG_SOURCES += $(PWD)/../hdl/FIFO2.v
all: dut  
dut:
	rm -rf sim_build
	$(MAKE) sim MODULE=test TOPLEVEL=dut
or:
	rm -rf sim_build
	$(MAKE) sim MODULE=or_test TOPLEVEL=or_test
ifc:
	rm -rf sim_build
	$(MAKE) sim MODULE=ifc_test TOPLEVEL=ifc_test
coverage:
	rm -rf sim_build
	$(MAKE) sim MODULE=ifc_coverage TOPLEVEL=ifc_test
include $(shell cocotb-config --makefiles)/Makefile.sim
