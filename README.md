# Dashboard-Gerencial-focado-na-experiencia-do-usu-rio-para-Tomada-de-Decis-es-Com-Power-BI
O objectivo do Dashboard é a análise das caracteristicas  dos paceintes de acordo a faixa etária numa unidade hospitalar, focado na experiencia do usuário aplicamos a proporção aurea no relatório e o criterio de posicionamento em Z para facilitar a visualização


- Criando um Dashboard para Tomada de Decisões Com Power BI
- Dashboard focado na experiencia do usuário, com aplicação da proporção aurea, criterio de posicionamento em Z(da esquerda para a direita, campo prinicpal e parte mais importante do relatório)
visualmente coenrente, aplicação das boas praticas.

Objectivos da visualização 
 - Objectivo geral -  análise das caracteristicas  dos paceintes de acordo a faixa etária na unidade hospitalar X
 - Objectivos específicos - De acordo com a faixa etária, avaliar o comportamento das variáveis (nº de pacientes por mês, sexo, Co morbilidade, Classificação, proveniência, diagnostico e destino)

# Trabalho Prático
- Fundo: hashtag treinamentos - https://www.hashtagtreinamentos.com/capa-para-dashboard-no-power-bi
- Icones: https://www.flaticon.com/ e https://www.freepik.com/

 - Excluimos as colunas desnecessárias para a análise;
 - Adicionamos coluna condicional para faixa etária apartir da coluna idade;
 - Ordenamos os meses cronologicamente com a criação de uma tabela D calendario

          (D_Calendario =
             ADDCOLUMNS(
               CALENDAR(DATE(2020,1,1), DATE(2030,12,31)),
              "Ano", YEAR([Date]), "Mes_Numero", MONTH([Date]),"Mes",
              VAR m = FORMAT([Date], "MMMM")
              RETURN UPPER(LEFT(m,1)) & MID(m,2,LEN(m)),
              "AnoMes", FORMAT([Date], "YYYY-MM")
        ) )
 - Criamos duas medidas DAX para cards só para masculinos e femininos a partir da coluna género, e fizemos o mesmo para pacientes com comorbidades
 
        (Total Masculino =
                  CALCULATE(
                     COUNTROWS(Tabela),
                       Tabela[Sexo] = "Masculino"
           ) )

 Em anexo o link do Dashboard:  https://app.powerbi.com/groups/me/reports/aaf287b9-8378-42bd-b9d5-9091b89bdda6/0127a8cd6251c6f347ba?experience=power-bi
