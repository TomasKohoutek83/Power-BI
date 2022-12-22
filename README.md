# Power-BI

DAX
    Vytvoreni Measures, Soucet jedne hodnoty z vice v jednom sloupci (WHS overview) - 
        Sum_Oper.20 = CALCULATE(sum(AE_Monthly_report[Confirmed_WHS]), FILTER(AE_Monthly_report,AE_Monthly_report[Operation] = "20"))
    Vytvoreni colum, Dosazeni tridici hodnoty na zaklade hodnoty ve sloupci (WHS overview) -  
        Split_WHS = SWITCH(AE_Monthly_report[Operation],"35",1,"50",1,"60",1,"70",1,"80",1,0)
