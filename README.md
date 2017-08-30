Elektrotehnički fakultet,
Univerzitet u Beogradu










PROJEKAT IZ PROGRAMSKIH PREVODILACA
NIVO A


















Asistent: Kojić Nemanja							Student: Stevanovic Ilija
										2011/0350


U Beogradu, jul 2016.





1.	Opis postavke zadatka

Potrebno je realizovati kompajler za programski jezik. Kompajler omogućava prevodjenje sintaksno i semantički ispravnih Mikrojava programa u Mikrojava bajtkod koji se izvršava na virtuelnoj mašini za Mikrojavu. Sintaksno i semantički ispravni Mikrojava programi su definisani specifikacijom.

2.	Generisanje kodova

1.	Prevođenje .flex napisanog koda se vrši komandom

-d src\rs\ac\bg\etf\pp1 spec\mjlexer.flex

pri čemu je JFlex.Main main klasa.

2.	Generisanje koda napisanog u mjparser.cup fajlu u klasu MJParser se vrši komandom

-destdir src\rs\ac\bg\etf\pp1 -parser MJParser spec\mjparser.cup

pri čemu je java_cup.Main main klasa.

3.	Generisanje Disasm se vrši komandom

test\program.obj

pri čemu je rs.etf.pp1.mj.runtime.disasm main klasa.

4.	Pokretanje programa se vrši komandom

test\program.obj

pri čemu je rs.etf.pp1.mj.runtime.Run main klasa.










3.	Generisanje parser koda

Generisanje parser koda ne javlja konflikte.

------- CUP v0.11a beta 20060608 Parser Generation Summary -------
 	0 errors and 0 warnings
  	45 terminals, 50 non-terminals, and 132 productions declared, 
  	producing 246 unique parse states.
  	0 terminals declared but not used.
  	0 non-terminals declared but not used.
  	0 productions never reduced.
  	0 conflicts detected (0 expected).
  	Code written to "MJParser.java", and "sym.java".
---------------------------------------------------- (v0.11a beta 20060608)

4.	Test primeri

Testovi za nivo A testiraju deklarisanje globalnih I lokalnih konstanti I promenljivih, kao I njihovo korišćenje. Nizovi I stringovi se ne koriste. Pojavljuje se samo main funkcija.
Testovi za nivo B testiraju, pored gore navedenoga, još I nizove I stringove, kao I postojanje više funkcija pored main-a. Klase se ne testiraju.

Test za fazu generisanja koda testira deklarisanje osnovnih tipova promenljivih I nizova, ne uključujući stringove. Postoji jedna glavna funkcija (main) I pozivaju se funkcije print I read. Takodje, mogu se pojavljivati I funkcije bez argumenata.
