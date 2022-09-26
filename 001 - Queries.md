1. Selecione todos os dados dos corretores. 

SELECT * FROM CORRETOR;

2. Selecione o nome do corretor, licença do corretor e todos os dados dos alugues negociados pelos seus respectivos corretores. 

SELECT C.NOME, C.LICENCA, I.* 
FROM CORRETOR AS C, ALUGUEL AS I 
WHERE C.CODCORR = I.CODCORR;


3. Busque a descricao do Imovel, valor do aluguel, e situação do imovel (se est=a alugado ou não) e o nome e telefone dos respectivos proprietarios. 

SELECT I.DESCRICAO, I.VALORAUGUEL, I.ALUGADO, P.NOME, P.TELEFONE 
FROM IMOVEL AS I, PROPRIETARIO AS P 
WHERE I.CODPROP = P.CODPROP;

4. Busque os Alugueis(codAlu, dataAlu e valorAluguel), com os respectivos nomes dos inquilinos e nome do corretor. 

SELECT  A.CODALU, A.DATAALUG, A.VALORAUGUEL, I.NOME, C.NOME 
FROM ALUGUEL AS A, INQUILINO AS I, CORRETOR AS C
WHERE A.CODINQ=I.CODINQ
AND A.CODCORR=C.CODCORR

5. Selecione a quantidade de imoveis alugados pelo corretor cuja licença é 'LC587'. 

SELECT COUNT(*) FROM 
ALUGUEL AS A, CORRETOR AS C
WHERE A.CODCORR = C.CODCORR
AND C.LICENCA='LC587'

6. Selecione os dados de todos os imóveis do Bill Gates que estão alugados. 

SELECT I.DESCRICAO, I.VALORAUGUEL
FROM IMOVEL AS I, PROPRIETARIO AS P
WHERE I.CODPROP=P.CODPROP
AND I.ALUGADO = TRUE
AND P.NOME = 'BILL GATES'

7. Selecione o nome do proprietario cujo contrato de aluguel está registrado sob o codigo (codAlu) = 6. 

SELECT P.NOME
FROM ALUGUEL AS A, PROPRIETARIO AS P, IMOVEL AS I
WHERE I.CODIMO=A.CODIMO
AND I.CODPROP = P.CODPROP
AND A.CODALU =6;

8. Quais são os proprietarios atendidos pelo corretor 'Alan Moore'? 

SELECT P.NOME
FROM PROPRIETARIO AS P, IMOVEL AS I, CORRETOR AS C, ALUGUEL AS A
WHERE I.CODIMO=A.CODIMO
AND I.CODPROP = P.CODPROP
AND C.CODCORR = A.CODCORR
AND C.NOME='ALAN MOORE';

9. Quem sao os inquilinos que pagam um aluguel superior a R$5000,00?

SELECT P.NOME
FROM PROPRIETARIO AS P, IMOVEL AS I, CORRETOR AS C, ALUGUEL AS A
WHERE I.CODIMO=A.CODIMO
AND I.CODPROP = P.CODPROP
AND C.CODCORR = A.CODCORR
AND C.NOME='ALAN MOORE';