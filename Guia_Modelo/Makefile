# Makefile para las guias de laboratorio.
#     - Permite compilar guia a guia o bien todas las guias.
#     - Elimina automaticamente los subproductos de la compilacion.
#
# Pablo Cobelli - Ultima modificacion: Agosto de 2015

all: 
	latexmk -pdf -silent Guia_Modelo.tex
	@make clean
	
clean:
	@rm -f *.log *.aux *.bbl *.blg *.idx *.toc *.out *.fdb_latexmk *.fls

clean-all:
	@make clean
	@rm -f *.pdf 
