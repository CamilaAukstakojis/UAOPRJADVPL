#include "totvs.ch"
#include "protheus.ch"

#Define Enter chr(13)+chr(10)


/*
ÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜÜ
ฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑ
ฑฑษออออออออออัออออออออออหอออออออัออออออออออออออออออออหออออออัอออออออออออออปฑฑ
ฑฑบPrograma  ณLOG       บAutor  ณMicrosiga           บ Data ณ  02/22/18   บฑฑ
ฑฑฬออออออออออุออออออออออสอออออออฯออออออออออออออออออออสออออออฯอออออออออออออนฑฑ
ฑฑบDesc.     ณ                                                            บฑฑ
ฑฑบ          ณ                                                            บฑฑ
ฑฑฬออออออออออุออออออออออออออออออออออออออออออออออออออออออออออออออออออออออออนฑฑ
ฑฑบUso       ณ AP                                                         บฑฑ
ฑฑศออออออออออฯออออออออออออออออออออออออออออออออออออออออออออออออออออออออออออผฑฑ
ฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑฑ
฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿฿
*/

User Function LogAmb()
Local aArea 	:= GetArea()
Local cFile 	:= ''
Local cExt		:= '.txt'
Local cPathServ := '\log\HelpDesk\'
Local cPathUser := ''
Local nHandle 	:= ''
Local cLog  	:= 'EOF'

// Nomeia o Arquivo a ser criado com a data YYYYMMDD
cFile := cValToChar(StrZero(Year(Date()),4) + Strzero(Month(Date()),2) + StrZero(Day(Date()),2)) + cExt

// TODO Gera Log para consulta
cLog := __CUSERID + ' - ' + StrTran(cValtoChar(Time()),':','')

//Verifica se existe o log do dia
If !File(cPathServ+cFile)
	//Cria o Arquivo de log
	nHandle := FCreate(cPathServ+cFile)               
	
	If nHandle = -1
		conout("Erro ao criar arquivo" + Str(Ferror()))
	Else
		FWrite(nHandle, cLog + Enter)
		FClose(nHandle)
	EndIf
Else
	//Abre o Arquivo de log
	nHandle := fOpen(cPathServ+cFile, FO_READWRITE + FO_SHARED)
	
	If nHandle = -1
		conout("Erro ao abrir arquivo" + Str(Ferror(),4))
	Else
		FSeek(nHandle,0,FS_END) //Posiciona no fim do Arquivo
		FWrite(nHandle, cLog + Enter)
		FClose(nHandle)
	EndIf
EndIf


RestArea(aArea)
Return()