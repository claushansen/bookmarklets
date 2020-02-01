## Bookmarklets af Claus Hansen


Her kan du finde de bookmarklets jeg har udviklet igennem tiden. Bare klik på den enkelte bookmarklet og træk linket til din bookmark linje i din browser.

## Generelle værktøjer
Disse bookmarklets er udviklet som forkellige hjælpeværktøjer.
### URL2QR
* <a href="javascript:(function()%7Bvar%20url%3DencodeURI(window.location.href)%2CGoogleQrUrl%3D%22https%3A%2F%2Fchart.googleapis.com%2Fchart%3Fcht%3Dqr%26chl%3D%22%2Burl%2B%22%26chs%3D400x400%22%3Bwindow.open(GoogleQrUrl%2C%22_blank%22)%7D)()">URL2QR</a>

Åbner en ny tab/window med en QR kode til siden

---
## Moodle
Disse bookmarklets er udviklet til moodle.
### Statistik over afleverede opgaver

* [Opgave Statistik](javascript:(function()%7Bvar%20student%20%3D%20%24('.page-header-headings%20h2').text()%3Bvar%20opgaveresult%20%3D%20%5B%5D%3Bvar%20alleOpgaver%20%3D%20%24('.submissionstatustable')%3Bvar%20antalOpgaver%20%3D%20alleOpgaver.length%3Bvar%20antalAfleverede%20%3D%20%24('.submissionstatussubmitted').length%3Bvar%20afleveringsprocent%20%3D%20Math.floor((antalAfleverede%20%2F%20antalOpgaver)%20*%20100)%3B%24('.submissionstatustable').parent('ul').prev('h4').each(function%20(index)%20%7Blet%20obj%20%3D%20%7B%7D%3Bobj.titel%20%3D%20%24(this).text()%3Blet%20findSubmitted%20%3D%20%24(alleOpgaver%5Bindex%5D).find('.submissionstatussubmitted')%3Bif%20(findSubmitted.length%20%3C%201)%20%7Bobj.afleveret%20%3D%20'Nej'%3B%7D%20else%20%7Bobj.afleveret%20%3D%20'Ja'%3B%7Dopgaveresult.push(obj)%3B%7D)%3Bopgaveresult%3Bfunction%20makeInfo()%20%7Bvar%20infoText%20%3D%20'%3Ch3%3E'%20%2B%20student%20%2B%20'%20har%20afleveret%20'%20%2B%20antalAfleverede%20%2B%20'%20ud%20af%20'%20%2B%20antalOpgaver%20%2B%20'%20opgaver.%3C%2Fh3%3E'%3BinfoText%20%2B%3D%20'%3Ch4%3EAfleveringsprocenten%20er%20derfor%20p%C3%A5%20'%20%2B%20afleveringsprocent%20%2B%20'%25.%3C%2Fh4%3E'%3BinfoText%20%2B%3D%20'%3Cb%3EOpgaver%20udf%C3%B8rt%3A%3C%2Fb%3E%3Cbr%3E'%3BinfoText%20%2B%3D%20'%3Cul%3E'%3Bfor%20(var%20i%20%3D%200%3B%20i%20%3C%20opgaveresult.length%3B%20i%2B%2B)%20%7BinfoText%20%2B%3D%20'%3Cli%3E'%3Blet%20color%20%3D%20opgaveresult%5Bi%5D.afleveret%20%3D%3D%20'Ja'%20%3F%20'green'%20%3A%20'red'%3BinfoText%20%2B%3D%20opgaveresult%5Bi%5D.titel%20%2B%20'%20%3A%20%3Cb%20style%3D%22color%3A'%20%2B%20color%20%2B%20'%22%3E'%20%2B%20opgaveresult%5Bi%5D.afleveret%20%2B%20'%3C%2Fb%3E'%3BinfoText%20%2B%3D%20'%3C%2Fli%3E'%3B%7DinfoText%20%2B%3D%20'%3C%2Ful%3E'%3Bvar%20infodiv%20%3D%20%24('%3Cdiv%20id%3D%22opgaveinfo%22%3E%3C%2Fdiv%3E')%3Binfodiv.css(%7B%20'background-color'%3A%20'%23FFF'%2C%20'padding'%3A%20'20px'%2C%20'margin-bottom'%3A%20'30px'%20%7D)%3Binfodiv.html(infoText)%3Binfodiv.insertBefore(%24('.page-context-header'))%3B%7DmakeInfo()%7D)())

Denne bookmarklet laver en hurtig oversigt over de afleverede opgave i Moodle: Betjeningspanel -> Mine kurser ->[Kursus] -> Deltagere -> [Elev] ->Rapporter -> Komplet rapport.

Træk dette link til dine bookmarks og klik på det, når du er på ovenstående side i Moodle. Så vises en overskuelig statistik over elevens afleverede opgaver, i toppen af siden.

---
## Elevplan
Disse bookmarklets er udviklet til elevplan

### Udtræk liste over elever tilstede

* <a href="javascript:(function()%7Bfor(var%20activetab%3Ddocument.querySelector('div%5Bid*%3D%22tabs-%22%5D%3Anot(.ui-tabs-hide')%2Celevrows%3Dactivetab.querySelectorAll('tr%5Bid*%3D%22tabs-%22%5D')%2CexportList%3D%22%22%2Ci%3D0%3Belevrows.length%3Ei%3Bi%2B%2B)%7Blet%20e%3Delevrows%5Bi%5D.cells%2Ct%3De%5B1%5D.childNodes%5B1%5D.title%2B%22%20%22%2Be%5B2%5D.childNodes%5B1%5D.title%2Co%3Delevrows%5Bi%5D.querySelectorAll(%22.ikkegodkendt%22).length%3E0%2Cl%3Delevrows%5Bi%5D.querySelectorAll(%22.godkendt%22).length%3E0%3Bo%7C%7Cl%7C%7C(exportList%2B%3Dt%2B%22%5Cn%22)%7Dfunction%20copyTextToClipboard(e)%7Bvar%20t%3Ddocument.createElement(%22textarea%22)%3Bt.value%3De%2Cdocument.body.appendChild(t)%2Ct.focus()%2Ct.select()%3Btry%7Bvar%20o%3Ddocument.execCommand(%22copy%22)%3Balert(%22Kopieringen%20af%20elevliste%20%22%2B(o%3F%22lykkedes%22%3A%22Fejlede%22))%7Dcatch(e)%7Balert(%22Oops%2C%20unable%20to%20copy%22%2Ce)%7Ddocument.body.removeChild(t)%7Dconsole.log(exportList)%2CcopyTextToClipboard(exportList)%7D)()">Kopier Elevliste</a>

Denne bookmarklet laver en hurtig liste over de elever der er tilstede på elevplan. 

Træk dette link til dine bookmarks og klik på det, når du er på fraværssiden side i elevplan. Så kopieres en liste over eleverne til din udklipsholder.

