# RPA-UIPATH-

## Robotic process automation projects using UiPath software.

## Turinys (Table of contents)
1. [Riešutų automatas](#riesutai)
2. [Prisijungimas prie svetainės, word, excel failo redagavimas, filmų paieška](#paragraph2)
3. [Duomenų nuskaitymas ir apdorojimas iš failo](#paragraph3)
4. [Valiutų kursų radimas interneto naršyklėje](#paragraph4)
5. [Elektroninių laiškų priedų atsisiuntimas ir apdorojimas](#paragraph5)

## Riešutų pardavimų automato realizacija (Realization of the nut vending machine):<a name="riesutai"></a>  

### Duomenų srauto diagrama (Flowchart):
![vpr](https://github.com/Mantelisx/RPA-UIPATH-/assets/92160605/0e4e693c-9fac-47ec-a47e-544d5c57e8e0)

### UiPath Studio aplinka (UiPath Studio editor):  
![paveikslas](https://github.com/Mantelisx/RPA-UIPATH-/assets/92160605/db2efd88-1dd1-46d8-89d6-e923c68ddae4)



### Riešutų pasirinkimo langas (Nut selection window):  
![paveikslas](https://github.com/Mantelisx/RPA-UIPATH-/assets/92160605/3a3572f7-f54d-4090-8f17-b6e4a39e74e9)

### Kiti langai (other windows):  
![paveikslas](https://github.com/Mantelisx/RPA-UIPATH-/assets/92160605/f01584ca-9610-4ff3-919f-f8329d194387)  
![paveikslas](https://github.com/Mantelisx/RPA-UIPATH-/assets/92160605/560c9a6e-3667-42ae-bd2b-dac66f163a33)  
![paveikslas](https://github.com/Mantelisx/RPA-UIPATH-/assets/92160605/93994d3a-2fa5-4b79-bcd0-d2ed3a31f9ec)  
![paveikslas](https://github.com/Mantelisx/RPA-UIPATH-/assets/92160605/59523c46-7af5-48a3-af6a-d7ab4b788e7c)  
![paveikslas](https://github.com/Mantelisx/RPA-UIPATH-/assets/92160605/0391ba6e-d424-4b5f-8126-81de3d1f3bdc)  
![paveikslas](https://github.com/Mantelisx/RPA-UIPATH-/assets/92160605/48e282c3-88a4-4150-9721-7c1f1ce0a502)  



## Prisijungimas prie svetainės, word failo redagavimas, filmų paieška: <a name="paragraph2"></a>  
### Prisijungimo informormacijos įvedimas:  
![paveikslas](https://github.com/Mantelisx/RPA-UIPATH-/assets/92160605/6bb62d4d-f216-41a0-bdf9-f6d2e3ce7498)  
### Automatinis informacijos „ištraukimas“ ir įrašymas į excel failą:  
![paveikslas](https://github.com/Mantelisx/RPA-UIPATH-/assets/92160605/fe2098fe-30fa-4b25-b8b3-92dc79c5975e)  
### Į teksto lauką suvedamas tekstas ir su UiPath Studio programos pagalba tekstas įrašomas į word failą:  
![paveikslas](https://github.com/Mantelisx/RPA-UIPATH-/assets/92160605/9eae829f-6352-4428-8df8-2fb2f64202a6)  
### Panašus veikimas ir su filmų paieška.





## Darbas su failais: <a name="paragraph3"></a>  
Roboto veikimo paaiškinimas: iš pradžių robotas nuskaito duotus failus (.csv, .xlsx), juose esančia informaciją išsaugo „DataTable“ formatu, tada sukuria informacinių lentelių struktūras, kurios po to bus panaudotos išvesti lentelei į .xlsx dokumentą (Rezultatai.xlsx). Po lentelių struktūros kūrimo yra nuspalvinamos .xlsx rezultatų failo atitinkamos vietos t.y. ruošiamas pateikimo dizainas. Toliau atliekami veiksmai yra skirti darbui su nuskaitytais failais: iš .csv failo gaunamas bankrutavimo statusas, kliento vardas, tada su .xlsx failu lyginami klientų vardai ir jei jie sutampa – pasikartojimų skaičius didinamas vienetu, sąskaitos suma pridedama prie to kliento galutinės sąskaitų sumos t.y. suma bus kaupiama. Galiausiai, turint anksčiau minėtą informaciją, robotukas ieško mažiausių/didžiausių (ne)bankrutavusių klientų sąskaitų, rūšiuoja klientus pagal bankrutavimo statusą (tam buvo galima naudoti „Filter Data Table“ veiklą pakeičiant didelę dalį roboto veiksenos, tačiau pasirinktas kitas būdas) bei išveda rezultatus į dokumento „Rezultatai.xlsx.“ atskirus „lapus“ „Bankrotas“, „Nebankrotas“ pagal tai ar klientai bankrutavę ar nebankrutavę.

### Duomenų srauto diagrama:  
![paveikslas](https://github.com/Mantelisx/RPA-UIPATH-/assets/92160605/81469f3c-47e7-41f5-b6b6-72e07341547c)  

### Automatiškai sukurto ir suformatuoto excel failo turinys:  
![paveikslas](https://github.com/Mantelisx/RPA-UIPATH-/assets/92160605/ec271b9e-acb4-41cd-a451-d934eab31159)  
### Įvesties duomenų failo turinio fragmentas:  
InvoiceID	ClientName	InvoiceValue  
1	Agitude	250  
2	Multiveo	200  
3	Unit&Products Inc.	210  
4	BiLane	160  
5	Epiloo	100  
6	Agitude	400  
7	Tech&Nation	250  
8	Tech&Nation	360  
9	Unindu	120  
10	Antinyx	850  
11	Tech&Nation	150  













## Valiutų kursų radimas: <a name="paragraph4"></a>  
Automatinio roboto veikimo aprašymas: atsidarius naują naršyklės langą įvedamas eurų į tam tikrą valiutą keitimo tekstas (pvz.: „eur to usd“), paimamos datos ir kurso reikšmės tuo metu kai buvo ieškoma (kada atnaujinta). Duomenys surašomi į lentelę („Valiutų kursai“) ir pagal tą pačią kursų lentelę užpildoma kita lentelė „Konvertuota valiuta“, kurioje pagal pateiktas eurų valiutos reikšmes apskaičiuojamos kitų valiutų reikšmės pagal valiutų kursą. Excel failo struktūra ir dizainas sukuriamas automatiškai.  
### Excel failo turinys:  
![paveikslas](https://github.com/Mantelisx/RPA-UIPATH-/assets/92160605/0337d4ef-3cc4-42b0-bf3d-b515f7edf472)  

### Visual Basic kodo fragmentas:  
![paveikslas](https://github.com/Mantelisx/RPA-UIPATH-/assets/92160605/347d1c57-5000-486a-ad8d-573c8e4edf47)  

## Elektroniniai laiškai: <a name="paragraph5"></a>  
Roboto veikimo paaiškinimas: iš nustatytos „Outlook 365“ paskyros robotukas pasirenka reikiamą laišką su priedais, juos išsaugo kataloge „Priedai“, taip pat, išsaugoma siuntėjo ir siuntimo laiko informacija. Kitame žingsnyje robotas sukuria lentelę („DataTable“), kurioje kaups duomenis iš sąskaitų faktūrų (šiame etape tie duomenys ir yra renkami). Vėliau visa sukaupta lentelė yra įrašoma į „6PD_ManJan.xlsx“ dokumentą, jis suformatuojamas ir išsaugomas. Galiausiai, nurodytam gavėjui išsiunčiamas laiškas su šabloniniu tekstu ir anksčiau minėtu dokumentu kaip priedu. 
