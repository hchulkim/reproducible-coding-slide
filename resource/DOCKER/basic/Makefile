# Makefile for analysis report
#

.PHONY: all clean

all: output/tables/processed_data.rds


output/tables/processed_data.rds: input/data/raw_data.rds input/code/test.R
	cd input/code && Rscript test.R

## Requires: https://github.com/lindenb/makefile2graph
dag: makefile-dag.png
makefile-dag.png: Makefile
	make -Bnd all | make2graph | dot -Tpng -Gdpi=300 -o makefile-dag.png

clean:
	rm -f output/tables/*
