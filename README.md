# banco_aph

@ -0,0 +1,104 @@
from  PyQt5  import  uic,QtWidgets
import mysql.connector 
""" from datetime import date
from datetime import time
from datetime import datetime """

banco = mysql.connector.connect(
    host="localhost",
    user="root",
    passwd="",
    database="sistema_aph" 
)


def primeira_tela ():

# aqui tem variaveis e radiobuntons


    variavel = lineEdit.text ()


    if primeira_tela.radioButton.isChecked() :
        print("variavel_2 foi selecionado")
        variavel_2 ="Masculino"

    print ("Variavel é:", variavel)



#FUNÇAO DE CONECTAR AO BANCO DE DADOS >>>>>>>>>"como esta no meu código" <<<<<<<<<<<

    cursor = banco.cursor()
    comando_SQL = "INSERT INTO tabela_1 (datax,viatura,n_ocorrencia,horax,nome,idade,local_ocorrencia,bairro,cidade,estado,sexo,tipo_de_ocorrencia,tipo_de_ocorrencia_2,tipo_de_ocorrencia_3, padrao_colisao,tipo_de_veiculo,codigo_oc) VALUES (%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s)"
    dados = (str(datax),str(viatura),str(n_ocorrencia),str(horax),str(nome),str(idade),str(local_ocorrencia),str(bairro),str(cidade),str(estado),sexo,tipo_de_ocorrencia,tipo_de_ocorrencia_2,tipo_de_ocorrencia_3,padrao_colisao,tipo_de_veiculo,codigo_oc)
    cursor.execute(comando_SQL,dados)
    banco.commit()

    primeira_tela.lineEdit.setText("")
    primeira_tela.lineEdit_2.setText("")
    primeira_tela.lineEdit_3.setText("")
    primeira_tela.lineEdit_4.setText("")
    primeira_tela.lineEdit_5.setText("")
    primeira_tela.lineEdit_6.setText("")
    primeira_tela.lineEdit_7.setText("")
    primeira_tela.lineEdit_8.setText("")
    primeira_tela.lineEdit_9.setText("")
    primeira_tela.lineEdit_10.setText("")

APLICO A MESMA LOGICA DE CIMA NA SEGUNDA PARTE DO CODIGO 
def chama_segunda_tela ():
    segunda_tela.show()

    descricao = segunda_tela.lineEdit.text()
    print ("", descricao)

    cursor = banco.cursor()
    comando_SQL = 'INSERT INTO tabela_2 (descricao) VALUES (%s)' #<<<<<   DA ERRO AQUI (agora se substituir por "descricao" 
    dados = (str(descricao))                                     # o código funciona porém não envia nada para o banco de Dados MySQL
    cursor.execute(comando_SQL, dados)
    banco.commit()

    segunda_tela.lineEdit.setText("") 




# CRIANDO BANCO DE DADOS
""" create database sistema_aph
    dafault charcter set utf8
    dafault collate utf8_general_ci; """

# CRIANDO TABELA 1

""" create table tabela_1 (
    `id` INT NOT NULL AUTO_INCREMENT,
    `datax` INT NOT NULL,
    `viatura` varchar (20) NOT NULL,
    `n_ocorrencia` INT NOT NULL,
    `horax` INT NOT NULL,
    `nome` varchar(100) NOT NULL DEFAULT 'PREJUDICADO',
    `idade` tinyint NOT NULL,
    `local_ocorrencia` varchar(100) NOT NULL DEFAULT 'PREJUDICADO',
    `bairro` varchar(50) NOT NULL DEFAULT 'PREJUDICADO',
    `cidade` varchar(50) NOT NULL DEFAULT 'PREJUDICADO',
    `estado` varchar(50) NOT NULL DEFAULT 'PREJUDICADO',
    `sexo` varchar(50) NOT NULL DEFAULT 'PREJUDICADO',
    `tipo_de_ocorrencia` varchar(50),
    `tipo_de_ocorrencia_2` varchar(50),
    `tipo_de_ocorrencia_3` varchar(50),
    `padrao_colisao` varchar(50),
    `tipo_de_veiculo` varchar(50),
    `codigo_oc` varchar (30),
    PRIMARY KEY (id)
) default charset = utf8; """


#>>>>>>>>>>>>>A SEGUNDA TABELA FOI CRIADA ASSSIM<<<<<<<<<<<<<<<<

""" create table tabela_2 (
    `id` INT NOT NULL AUTO_INCREMENT,
    `descricao` INT NOT NULL varchar (100);
    PRIMARY KEY (id)
) default charset = utf8; """ """
