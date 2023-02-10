# Power-BI

DAX
    Vytvoreni Measures, Soucet jedne hodnoty z vice v jednom sloupci (WHS overview) - 
        Sum_Oper.20 = CALCULATE(sum(AE_Monthly_report[Confirmed_WHS]), FILTER(AE_Monthly_report,AE_Monthly_report[Operation] = "20"))
    Vytvoreni colum, Dosazeni tridici hodnoty na zaklade hodnoty ve sloupci (WHS overview) -  
        Split_WHS = SWITCH(AE_Monthly_report[Operation],"35",1,"50",1,"60",1,"70",1,"80",1,0)
        
Reseni pro spojeni tabulek v pripade many to one a one ti one . Vytvoreni tabulky v power query.
        Pouzito v Weekly  overview reportu pri zjisteni odhlasenych hodin vs planovane hodiny.
        https://www.youtube.com/watch?v=vAvQ8pCnWDk

Workday - jak zjistit a zpocitat jejich pocet + svatky a pod.  Pouzito v capagrafu 
        https://translate.google.com/?hl=cs&sl=en&tl=cs&text=To%20verify%20we%20have%20285%20working%20days%20spent%20on%20Fencing%2C%20we%20can%20check%20in%20the%20DatesTable%20using%20filters%20to%20only%20show%20rows%20of%20dates%20between%20%2213%2F04%2F2020%22%20and%20%2229%2F05%2F2021%22.%20This%20is%20demonstrated%20in%20the%20diagrams%20below.&op=translate
