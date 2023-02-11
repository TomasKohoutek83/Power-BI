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


Calculate - odcitani dvou funkci calculate v jednom sloupci 
            Priklady a definice
            

                Předpokládejme, že máme tabulku s názvem "Sales" s následujícími sloupci:

                Date	Region	Sales
                2020-01-01	North	100
                2020-01-01	South	200
                2020-01-02	North	150
                2020-01-02	South	175
                Chceme vytvořit sloupec, který bude obsahovat rozdíl mezi prodeji v regionu "North" a "South". Můžeme to udělat následovně:

                            = CALCULATE(SUM(Sales[Sales]), FILTER(Sales, Sales[Region] = "North")) - CALCULATE(SUM(Sales[Sales]), FILTER(Sales, Sales[Region] =                                         "South"))
                Funkce CALCULATE používá funkci SUM k sčítání hodnot sloupce Sales pouze pro řádky, které splňují filtr definovaný funkcí FILTER. První volání                         CALCULATE výpočítá součet prodejů v regionu "North" a druhé volání výpočítá součet prodejů v regionu "South". Poté se oba výsledky odčítají a výsledek                 se vrátí jako hodnota nového sloupce.

                Výsledný sloupec by měl vypadat následovně:

                Date	Region	Sales	North-South Sales
                2020-01-01	North	100	-100
                2020-01-01	South	200	-100
                2020-01-02	North	150	-25
                2020-01-02	South	175	-25
