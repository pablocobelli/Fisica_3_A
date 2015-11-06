# Makefile para las guias de laboratorio.
#     - Permite compilar guia a guia o bien todas las guias.
#     - Elimina automaticamente los subproductos de la compilacion.
#
# Pablo Cobelli - Ultima modificacion: Agosto de 2015

all: 
	@make G01
	@make G02
	@make G03
	@make G04
	@make G05
	@make G06
	@make G07
	@make G08
	@make G09
	@make G10
	@make G11
	@make G12
	@echo " "
	@echo "Todas las guias fueron compiladas con exito."
	@make clean
	
G01: Guia_01_Electrostatica.tex
	latexmk -pdf -silent Guia_01_Electrostatica.tex

G02: Guia_02_Ley_de_Ohm.tex
	latexmk -pdf -silent Guia_02_Ley_de_Ohm.tex

G03: Guia_03_Magnetismo.tex
	latexmk -pdf -silent Guia_03_Magnetismo.tex

G04: Guia_04_Induccion.tex
	latexmk -pdf -silent Guia_04_Induccion.tex

G05: Guia_05_Circuito_RC.tex
	latexmk -pdf -silent Guia_05_Circuito_RC.tex

G06: Guia_06_Circuito_RLC.tex
	latexmk -pdf -silent Guia_06_Circuito_RLC.tex

G07: Guia_07_Ondas_en_una_cuerda.tex
	latexmk -pdf -silent Guia_07_Ondas_en_una_cuerda.tex

G08: Guia_08_Ondas_acusticas.tex
	latexmk -pdf -silent Guia_08_Ondas_acusticas.tex

G09: Guia_09_Interferencia.tex
	latexmk -pdf -silent Guia_09_Interferencia.tex

G10: Guia_10_Difraccion.tex
	latexmk -pdf -silent Guia_10_Difraccion.tex

G11: Guia_11_Redes_de_difraccion.tex
	latexmk -pdf -silent Guia_11_Redes_de_difraccion.tex

G12: Guia_12_Polarizacion.tex
	latexmk -pdf -silent Guia_12_Polarizacion.tex

clean:
	@rm -f *.log *.aux *.bbl *.blg *.idx *.toc *.out *.fdb_latexmk *.fls

clean-all:
	@make clean
	@rm -f *.pdf 
