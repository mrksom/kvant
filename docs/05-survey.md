
# (PART) Valimiuuringud {-} 

# Valimiuuringud




## Tõenäosuslik valim (probability sample)

Järeldava statistika kontseptsioonid eeldavad üldjuhul alati nn juhuvalimit. Juhuslikkus tähedab siikohal, et kõikidel üldkogumi liikmetel on valimisse sattumiseks võrdne tõenäosus. [Suurte numbrite seadus]('https://en.wikipedia.org/wiki/Law_of_large_numbers) (*the law of large numbers*) viitab, et ükskõik millise üldkogumi kohta vjärelduste tegemiseks oleks meil sellest üldkogumist vaja umbes 1000 vaatluselist valimit. Kui me küsiksime Eestis 1000 inimese käest nende sissetuleku suurust, siis 1000 inimese keskmine sissetulek peaks olema küllaltki lähedane terve Eesti keskmise sissetulekuga. Seda aga ainult juhul, kui need 1000 inimest on valitud juhuslikult (kõikidel eestlastel peaks olema võrdne võimalus sattuda nende 1000 sekka). Mis juhtuks, kui me juhusliku valimi asemel võtaksime hoopis igast maakonnast 67 inimest (Eestis on 15 maakonda, seega $1000 \div 15 \approx 67$). Tõenäoliselt me alahindaksime keskmist sissetulekut oluliselt. Kõige suuremate sissetulekutega ja samas kõige suurema rahvaarvuga maakond on Harjumaa (598059 inimest 2019 aastal). Kõige väiksemate sissetulekutega ja ka rahvaarvult kõige väiksem maakond on Hiiu maakond (9387 inimest 2019 aastal). Kui me käsitleme mõlemat maakonda võrdselt, siis keskmise arvutamisel võtaksime Hiiu maakonna väikesed sissetulekud arvesse ebaproportsionaalselt suurel määral ja Harjumaa kõrgemad sissetulekud ebaproportsionaalselt väikesel määral (Hiiumaa on üleesindatud ja Harjumaa on alaesindatud). Meie maakondade põhine valim ei oleks enam üldkogumi suhtes __representatiivne__.

Oletame, et arvutame igas maakonnas 67 inimese põhjal selle maakonna keskmise sissetuleku.


```{=html}
<div class="tabwid"><style>.cl-3a7e5b10{}.cl-3a72488e{font-family:'Arial';font-size:11pt;font-weight:normal;font-style:normal;text-decoration:none;color:rgba(0, 0, 0, 1.00);background-color:transparent;}.cl-3a775f36{margin:0;text-align:left;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);padding-bottom:5pt;padding-top:5pt;padding-left:5pt;padding-right:5pt;line-height: 1;background-color:transparent;}.cl-3a775f40{margin:0;text-align:right;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);padding-bottom:5pt;padding-top:5pt;padding-left:5pt;padding-right:5pt;line-height: 1;background-color:transparent;}.cl-3a77839e{width:1.704in;background-color:transparent;vertical-align: middle;border-bottom: 1.5pt solid rgba(102, 102, 102, 1.00);border-top: 1.5pt solid rgba(102, 102, 102, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3a7783a8{width:1.873in;background-color:transparent;vertical-align: middle;border-bottom: 1.5pt solid rgba(102, 102, 102, 1.00);border-top: 1.5pt solid rgba(102, 102, 102, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3a7783a9{width:0.939in;background-color:transparent;vertical-align: middle;border-bottom: 1.5pt solid rgba(102, 102, 102, 1.00);border-top: 1.5pt solid rgba(102, 102, 102, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3a7783b2{width:1.704in;background-color:transparent;vertical-align: middle;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3a7783b3{width:1.873in;background-color:transparent;vertical-align: middle;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3a7783b4{width:0.939in;background-color:transparent;vertical-align: middle;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3a7783bc{width:1.704in;background-color:transparent;vertical-align: middle;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3a7783bd{width:1.873in;background-color:transparent;vertical-align: middle;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3a7783be{width:0.939in;background-color:transparent;vertical-align: middle;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3a7783c6{width:1.704in;background-color:transparent;vertical-align: middle;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3a7783c7{width:1.873in;background-color:transparent;vertical-align: middle;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3a7783d0{width:0.939in;background-color:transparent;vertical-align: middle;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3a7783d1{width:1.704in;background-color:transparent;vertical-align: middle;border-bottom: 1.5pt solid rgba(102, 102, 102, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3a7783d2{width:1.873in;background-color:transparent;vertical-align: middle;border-bottom: 1.5pt solid rgba(102, 102, 102, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3a7783d3{width:0.939in;background-color:transparent;vertical-align: middle;border-bottom: 1.5pt solid rgba(102, 102, 102, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}</style><table data-quarto-disable-processing='true' class='cl-3a7e5b10'>

```

<caption style="display:table-caption;">(\#tab:unnamed-chunk-1)<span>Eesti maakondade keskmised brutopalgad 2019 (Statistikaamet)</span></caption>

```{=html}

<thead><tr style="overflow-wrap:break-word;"><th class="cl-3a77839e"><p class="cl-3a775f36"><span class="cl-3a72488e">Maakond</span></p></th><th class="cl-3a7783a8"><p class="cl-3a775f40"><span class="cl-3a72488e">Keskmine brutokuupalk</span></p></th><th class="cl-3a7783a9"><p class="cl-3a775f40"><span class="cl-3a72488e">Rahvaarv</span></p></th></tr></thead><tbody><tr style="overflow-wrap:break-word;"><td class="cl-3a7783b2"><p class="cl-3a775f36"><span class="cl-3a72488e">Harju maakond</span></p></td><td class="cl-3a7783b3"><p class="cl-3a775f40"><span class="cl-3a72488e">1 531</span></p></td><td class="cl-3a7783b4"><p class="cl-3a775f40"><span class="cl-3a72488e">598 059</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3a7783bc"><p class="cl-3a775f36"><span class="cl-3a72488e">Hiiu maakond</span></p></td><td class="cl-3a7783bd"><p class="cl-3a775f40"><span class="cl-3a72488e">993</span></p></td><td class="cl-3a7783be"><p class="cl-3a775f40"><span class="cl-3a72488e">9 387</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3a7783bc"><p class="cl-3a775f36"><span class="cl-3a72488e">Ida-Viru maakond</span></p></td><td class="cl-3a7783bd"><p class="cl-3a775f40"><span class="cl-3a72488e">1 147</span></p></td><td class="cl-3a7783be"><p class="cl-3a775f40"><span class="cl-3a72488e">136 240</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3a7783b2"><p class="cl-3a775f36"><span class="cl-3a72488e">Jõgeva maakond</span></p></td><td class="cl-3a7783b3"><p class="cl-3a775f40"><span class="cl-3a72488e">1 066</span></p></td><td class="cl-3a7783b4"><p class="cl-3a775f40"><span class="cl-3a72488e">28 734</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3a7783bc"><p class="cl-3a775f36"><span class="cl-3a72488e">Järva maakond</span></p></td><td class="cl-3a7783bd"><p class="cl-3a775f40"><span class="cl-3a72488e">1 192</span></p></td><td class="cl-3a7783be"><p class="cl-3a775f40"><span class="cl-3a72488e">30 286</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3a7783bc"><p class="cl-3a775f36"><span class="cl-3a72488e">Lääne maakond</span></p></td><td class="cl-3a7783bd"><p class="cl-3a775f40"><span class="cl-3a72488e">1 274</span></p></td><td class="cl-3a7783be"><p class="cl-3a775f40"><span class="cl-3a72488e">20 507</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3a7783bc"><p class="cl-3a775f36"><span class="cl-3a72488e">Lääne-Viru maakond</span></p></td><td class="cl-3a7783bd"><p class="cl-3a775f40"><span class="cl-3a72488e">1 095</span></p></td><td class="cl-3a7783be"><p class="cl-3a775f40"><span class="cl-3a72488e">59 325</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3a7783bc"><p class="cl-3a775f36"><span class="cl-3a72488e">Põlva maakond</span></p></td><td class="cl-3a7783bd"><p class="cl-3a775f40"><span class="cl-3a72488e">1 140</span></p></td><td class="cl-3a7783be"><p class="cl-3a775f40"><span class="cl-3a72488e">25 006</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3a7783bc"><p class="cl-3a775f36"><span class="cl-3a72488e">Pärnu maakond</span></p></td><td class="cl-3a7783bd"><p class="cl-3a775f40"><span class="cl-3a72488e">1 172</span></p></td><td class="cl-3a7783be"><p class="cl-3a775f40"><span class="cl-3a72488e">85 938</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3a7783c6"><p class="cl-3a775f36"><span class="cl-3a72488e">Rapla maakond</span></p></td><td class="cl-3a7783c7"><p class="cl-3a775f40"><span class="cl-3a72488e">1 200</span></p></td><td class="cl-3a7783d0"><p class="cl-3a775f40"><span class="cl-3a72488e">33 311</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3a7783bc"><p class="cl-3a775f36"><span class="cl-3a72488e">Saare maakond</span></p></td><td class="cl-3a7783bd"><p class="cl-3a775f40"><span class="cl-3a72488e">1 082</span></p></td><td class="cl-3a7783be"><p class="cl-3a775f40"><span class="cl-3a72488e">33 108</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3a7783bc"><p class="cl-3a775f36"><span class="cl-3a72488e">Tartu maakond</span></p></td><td class="cl-3a7783bd"><p class="cl-3a775f40"><span class="cl-3a72488e">1 426</span></p></td><td class="cl-3a7783be"><p class="cl-3a775f40"><span class="cl-3a72488e">152 976</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3a7783b2"><p class="cl-3a775f36"><span class="cl-3a72488e">Valga maakond</span></p></td><td class="cl-3a7783b3"><p class="cl-3a775f40"><span class="cl-3a72488e">1 058</span></p></td><td class="cl-3a7783b4"><p class="cl-3a775f40"><span class="cl-3a72488e">28 370</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3a7783b2"><p class="cl-3a775f36"><span class="cl-3a72488e">Viljandi maakond</span></p></td><td class="cl-3a7783b3"><p class="cl-3a775f40"><span class="cl-3a72488e">1 201</span></p></td><td class="cl-3a7783b4"><p class="cl-3a775f40"><span class="cl-3a72488e">46 371</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3a7783d1"><p class="cl-3a775f36"><span class="cl-3a72488e">Võru maakond</span></p></td><td class="cl-3a7783d2"><p class="cl-3a775f40"><span class="cl-3a72488e">1 113</span></p></td><td class="cl-3a7783d3"><p class="cl-3a775f40"><span class="cl-3a72488e">35 782</span></p></td></tr></tbody></table></div>
```

Kui me nüüd arvutaksime Eesti keskmise sissetuleku lähtuvalt maakondade keskmistest sissetulekutest, siis saaksime vastuseks: 

$$\frac{1531 + 993 + ... + 1113}{15} = 1179$$ 

Statistikaameti järgi oli Eesti keskmine sissetulek 2019 aastal aga 1407 eurot. Seega meie hinnang alahindab oluliselt tegelikku keskmist sissetulekut.

Võttes oma valimisse igast maakonnast 67 inimest, ei ole meie valim küll enam juhuvalim, kuid niikaua kuni me teame kõikide maakondade rahvaarvu, on see siiski __tõenäosuslik valim__ (antud juhul stratifitseeritud valim). Seda seetõttu, et kõikidel Eesti inimestel on ikkagi võimalus sellesse valimisse sattuda. Harjumaa inimestel küll väiksem ja Hiiumaa inimestel suurem, kuid mingi võimalus on kõigil. Kui me nüüd seda erinevat valimisse sattmise tõenäosust teame, siis on meil võimalik mitte-representatiivne valim representatiivseks muuta. Selleks tuleb meil Hiiumaa elanikud väiksemaks ja Harjumaa elanikud suuremaks kaaluda. Seejärel saame (mõningate mööndustega) jälle kasutada järeldava statistika meetodeid ning teha nende alusel korrektseid järeldusi üldkogumi kohta. 

## Kaalud

### Valimi kaalud

Kõikide Harjumaa elanike jaoks oleks tõenäosus meie valimisse sattuda $67  \div 598059 \approx 0.0001120$. Kõigi Hiiumaa elanike jaoks oleks see tõenäosus $67  \div 9387 \approx 0.0071375$. Harjumaa valimis esindaks iga valimisse sattunu $1 \div 0.00011 \approx 8926$ inimest ja Hiiumaal $1 \div 0.0071 \approx 140$ inimest. Seega, kui teame iga inimese valimisse sattumise tõenäosust $\pi$, siis saame nende alusel välja arvutada selle, mitut üldkogumi inimest see valimisse sattunud inimene esindab, ehk iga valimi vaatluse __valimi kaalud__ $\frac{1}{\pi}$ (nimetatakse ka disainikaaludeks ehk *design weights* või ka *base weights*). Valimi kaalude suurus on pöördvõrdeline valimisse sattumise tõenäosusega: 

$$w_i = \frac{1}{\pi_i}$$

kusjuures üldkogumi suurs on võrdne kaalude summaga:

$$P = \sum^{n}_{i = 1} w_i$$
ja mingi tunnuse $y$ üldkogumi kogusumma on: 

$$T_y = \sum^{n}_{i = 1}w_i y_i$$
Kui me rakendame neid kaale erinevates maakodades elavatele inimestele, siis saame alaesindatud maakonna (Harjumaa) valimi üles kaaluda $67 \times 8926 = 598042$ ja üleesindatud maakona (Hiiumaa) valimi alla kaaluda $67 \times 140 = 9380$ (erinevused algsetest maakondade suurustest on tingitud ümardamisest, kui ei oleks seda teinud, oleksid tulemused identsed).


```{=html}
<div class="tabwid"><style>.cl-3ac83762{}.cl-3abcac44{font-family:'Arial';font-size:11pt;font-weight:normal;font-style:normal;text-decoration:none;color:rgba(0, 0, 0, 1.00);background-color:transparent;}.cl-3ac16112{margin:0;text-align:left;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);padding-bottom:5pt;padding-top:5pt;padding-left:5pt;padding-right:5pt;line-height: 1;background-color:transparent;}.cl-3ac1611c{margin:0;text-align:right;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);padding-bottom:5pt;padding-top:5pt;padding-left:5pt;padding-right:5pt;line-height: 1;background-color:transparent;}.cl-3ac18020{width:1.704in;background-color:transparent;vertical-align: middle;border-bottom: 1.5pt solid rgba(102, 102, 102, 1.00);border-top: 1.5pt solid rgba(102, 102, 102, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3ac1802a{width:0.837in;background-color:transparent;vertical-align: middle;border-bottom: 1.5pt solid rgba(102, 102, 102, 1.00);border-top: 1.5pt solid rgba(102, 102, 102, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3ac1802b{width:0.455in;background-color:transparent;vertical-align: middle;border-bottom: 1.5pt solid rgba(102, 102, 102, 1.00);border-top: 1.5pt solid rgba(102, 102, 102, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3ac18034{width:1.262in;background-color:transparent;vertical-align: middle;border-bottom: 1.5pt solid rgba(102, 102, 102, 1.00);border-top: 1.5pt solid rgba(102, 102, 102, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3ac1803e{width:1.05in;background-color:transparent;vertical-align: middle;border-bottom: 1.5pt solid rgba(102, 102, 102, 1.00);border-top: 1.5pt solid rgba(102, 102, 102, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3ac1803f{width:1.704in;background-color:transparent;vertical-align: middle;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3ac18040{width:0.837in;background-color:transparent;vertical-align: middle;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3ac18048{width:0.455in;background-color:transparent;vertical-align: middle;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3ac18049{width:1.262in;background-color:transparent;vertical-align: middle;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3ac18052{width:1.05in;background-color:transparent;vertical-align: middle;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3ac18053{width:1.704in;background-color:transparent;vertical-align: middle;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3ac18054{width:0.837in;background-color:transparent;vertical-align: middle;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3ac1805c{width:0.455in;background-color:transparent;vertical-align: middle;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3ac1805d{width:1.262in;background-color:transparent;vertical-align: middle;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3ac18066{width:1.05in;background-color:transparent;vertical-align: middle;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3ac18067{width:1.704in;background-color:transparent;vertical-align: middle;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3ac18068{width:0.837in;background-color:transparent;vertical-align: middle;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3ac18070{width:0.455in;background-color:transparent;vertical-align: middle;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3ac1807a{width:1.262in;background-color:transparent;vertical-align: middle;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3ac1807b{width:1.05in;background-color:transparent;vertical-align: middle;border-bottom: 0 solid rgba(0, 0, 0, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3ac1807c{width:1.704in;background-color:transparent;vertical-align: middle;border-bottom: 1.5pt solid rgba(102, 102, 102, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3ac18084{width:0.837in;background-color:transparent;vertical-align: middle;border-bottom: 1.5pt solid rgba(102, 102, 102, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3ac18085{width:0.455in;background-color:transparent;vertical-align: middle;border-bottom: 1.5pt solid rgba(102, 102, 102, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3ac18086{width:1.262in;background-color:transparent;vertical-align: middle;border-bottom: 1.5pt solid rgba(102, 102, 102, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}.cl-3ac1808e{width:1.05in;background-color:transparent;vertical-align: middle;border-bottom: 1.5pt solid rgba(102, 102, 102, 1.00);border-top: 0 solid rgba(0, 0, 0, 1.00);border-left: 0 solid rgba(0, 0, 0, 1.00);border-right: 0 solid rgba(0, 0, 0, 1.00);margin-bottom:0;margin-top:0;margin-left:0;margin-right:0;}</style><table data-quarto-disable-processing='true' class='cl-3ac83762'>

```

<caption style="display:table-caption;">(\#tab:unnamed-chunk-2)<span>Eesti maakondade kaalud rahvaarvu alusel (Statistikaamet)</span></caption>

```{=html}

<thead><tr style="overflow-wrap:break-word;"><th class="cl-3ac18020"><p class="cl-3ac16112"><span class="cl-3abcac44">Maakond</span></p></th><th class="cl-3ac1802a"><p class="cl-3ac1611c"><span class="cl-3abcac44">N</span></p></th><th class="cl-3ac1802b"><p class="cl-3ac1611c"><span class="cl-3abcac44">n</span></p></th><th class="cl-3ac18034"><p class="cl-3ac1611c"><span class="cl-3abcac44">Tõenäosus</span></p></th><th class="cl-3ac1803e"><p class="cl-3ac1611c"><span class="cl-3abcac44">Kaalud</span></p></th></tr></thead><tbody><tr style="overflow-wrap:break-word;"><td class="cl-3ac1803f"><p class="cl-3ac16112"><span class="cl-3abcac44">Harju maakond</span></p></td><td class="cl-3ac18040"><p class="cl-3ac1611c"><span class="cl-3abcac44">598 059</span></p></td><td class="cl-3ac18048"><p class="cl-3ac1611c"><span class="cl-3abcac44">67</span></p></td><td class="cl-3ac18049"><p class="cl-3ac1611c"><span class="cl-3abcac44">0,0001</span></p></td><td class="cl-3ac18052"><p class="cl-3ac1611c"><span class="cl-3abcac44">8 926,3</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3ac18053"><p class="cl-3ac16112"><span class="cl-3abcac44">Hiiu maakond</span></p></td><td class="cl-3ac18054"><p class="cl-3ac1611c"><span class="cl-3abcac44">9 387</span></p></td><td class="cl-3ac1805c"><p class="cl-3ac1611c"><span class="cl-3abcac44">67</span></p></td><td class="cl-3ac1805d"><p class="cl-3ac1611c"><span class="cl-3abcac44">0,0071</span></p></td><td class="cl-3ac18066"><p class="cl-3ac1611c"><span class="cl-3abcac44">140,1</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3ac18053"><p class="cl-3ac16112"><span class="cl-3abcac44">Ida-Viru maakond</span></p></td><td class="cl-3ac18054"><p class="cl-3ac1611c"><span class="cl-3abcac44">136 240</span></p></td><td class="cl-3ac1805c"><p class="cl-3ac1611c"><span class="cl-3abcac44">67</span></p></td><td class="cl-3ac1805d"><p class="cl-3ac1611c"><span class="cl-3abcac44">0,0005</span></p></td><td class="cl-3ac18066"><p class="cl-3ac1611c"><span class="cl-3abcac44">2 033,4</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3ac1803f"><p class="cl-3ac16112"><span class="cl-3abcac44">Jõgeva maakond</span></p></td><td class="cl-3ac18040"><p class="cl-3ac1611c"><span class="cl-3abcac44">28 734</span></p></td><td class="cl-3ac18048"><p class="cl-3ac1611c"><span class="cl-3abcac44">67</span></p></td><td class="cl-3ac18049"><p class="cl-3ac1611c"><span class="cl-3abcac44">0,0023</span></p></td><td class="cl-3ac18052"><p class="cl-3ac1611c"><span class="cl-3abcac44">428,9</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3ac18053"><p class="cl-3ac16112"><span class="cl-3abcac44">Järva maakond</span></p></td><td class="cl-3ac18054"><p class="cl-3ac1611c"><span class="cl-3abcac44">30 286</span></p></td><td class="cl-3ac1805c"><p class="cl-3ac1611c"><span class="cl-3abcac44">67</span></p></td><td class="cl-3ac1805d"><p class="cl-3ac1611c"><span class="cl-3abcac44">0,0022</span></p></td><td class="cl-3ac18066"><p class="cl-3ac1611c"><span class="cl-3abcac44">452,0</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3ac18053"><p class="cl-3ac16112"><span class="cl-3abcac44">Lääne maakond</span></p></td><td class="cl-3ac18054"><p class="cl-3ac1611c"><span class="cl-3abcac44">20 507</span></p></td><td class="cl-3ac1805c"><p class="cl-3ac1611c"><span class="cl-3abcac44">67</span></p></td><td class="cl-3ac1805d"><p class="cl-3ac1611c"><span class="cl-3abcac44">0,0033</span></p></td><td class="cl-3ac18066"><p class="cl-3ac1611c"><span class="cl-3abcac44">306,1</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3ac18053"><p class="cl-3ac16112"><span class="cl-3abcac44">Lääne-Viru maakond</span></p></td><td class="cl-3ac18054"><p class="cl-3ac1611c"><span class="cl-3abcac44">59 325</span></p></td><td class="cl-3ac1805c"><p class="cl-3ac1611c"><span class="cl-3abcac44">67</span></p></td><td class="cl-3ac1805d"><p class="cl-3ac1611c"><span class="cl-3abcac44">0,0011</span></p></td><td class="cl-3ac18066"><p class="cl-3ac1611c"><span class="cl-3abcac44">885,4</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3ac18053"><p class="cl-3ac16112"><span class="cl-3abcac44">Põlva maakond</span></p></td><td class="cl-3ac18054"><p class="cl-3ac1611c"><span class="cl-3abcac44">25 006</span></p></td><td class="cl-3ac1805c"><p class="cl-3ac1611c"><span class="cl-3abcac44">67</span></p></td><td class="cl-3ac1805d"><p class="cl-3ac1611c"><span class="cl-3abcac44">0,0027</span></p></td><td class="cl-3ac18066"><p class="cl-3ac1611c"><span class="cl-3abcac44">373,2</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3ac18053"><p class="cl-3ac16112"><span class="cl-3abcac44">Pärnu maakond</span></p></td><td class="cl-3ac18054"><p class="cl-3ac1611c"><span class="cl-3abcac44">85 938</span></p></td><td class="cl-3ac1805c"><p class="cl-3ac1611c"><span class="cl-3abcac44">67</span></p></td><td class="cl-3ac1805d"><p class="cl-3ac1611c"><span class="cl-3abcac44">0,0008</span></p></td><td class="cl-3ac18066"><p class="cl-3ac1611c"><span class="cl-3abcac44">1 282,7</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3ac18067"><p class="cl-3ac16112"><span class="cl-3abcac44">Rapla maakond</span></p></td><td class="cl-3ac18068"><p class="cl-3ac1611c"><span class="cl-3abcac44">33 311</span></p></td><td class="cl-3ac18070"><p class="cl-3ac1611c"><span class="cl-3abcac44">67</span></p></td><td class="cl-3ac1807a"><p class="cl-3ac1611c"><span class="cl-3abcac44">0,0020</span></p></td><td class="cl-3ac1807b"><p class="cl-3ac1611c"><span class="cl-3abcac44">497,2</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3ac18053"><p class="cl-3ac16112"><span class="cl-3abcac44">Saare maakond</span></p></td><td class="cl-3ac18054"><p class="cl-3ac1611c"><span class="cl-3abcac44">33 108</span></p></td><td class="cl-3ac1805c"><p class="cl-3ac1611c"><span class="cl-3abcac44">67</span></p></td><td class="cl-3ac1805d"><p class="cl-3ac1611c"><span class="cl-3abcac44">0,0020</span></p></td><td class="cl-3ac18066"><p class="cl-3ac1611c"><span class="cl-3abcac44">494,1</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3ac18053"><p class="cl-3ac16112"><span class="cl-3abcac44">Tartu maakond</span></p></td><td class="cl-3ac18054"><p class="cl-3ac1611c"><span class="cl-3abcac44">152 976</span></p></td><td class="cl-3ac1805c"><p class="cl-3ac1611c"><span class="cl-3abcac44">67</span></p></td><td class="cl-3ac1805d"><p class="cl-3ac1611c"><span class="cl-3abcac44">0,0004</span></p></td><td class="cl-3ac18066"><p class="cl-3ac1611c"><span class="cl-3abcac44">2 283,2</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3ac1803f"><p class="cl-3ac16112"><span class="cl-3abcac44">Valga maakond</span></p></td><td class="cl-3ac18040"><p class="cl-3ac1611c"><span class="cl-3abcac44">28 370</span></p></td><td class="cl-3ac18048"><p class="cl-3ac1611c"><span class="cl-3abcac44">67</span></p></td><td class="cl-3ac18049"><p class="cl-3ac1611c"><span class="cl-3abcac44">0,0024</span></p></td><td class="cl-3ac18052"><p class="cl-3ac1611c"><span class="cl-3abcac44">423,4</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3ac1803f"><p class="cl-3ac16112"><span class="cl-3abcac44">Viljandi maakond</span></p></td><td class="cl-3ac18040"><p class="cl-3ac1611c"><span class="cl-3abcac44">46 371</span></p></td><td class="cl-3ac18048"><p class="cl-3ac1611c"><span class="cl-3abcac44">67</span></p></td><td class="cl-3ac18049"><p class="cl-3ac1611c"><span class="cl-3abcac44">0,0014</span></p></td><td class="cl-3ac18052"><p class="cl-3ac1611c"><span class="cl-3abcac44">692,1</span></p></td></tr><tr style="overflow-wrap:break-word;"><td class="cl-3ac1807c"><p class="cl-3ac16112"><span class="cl-3abcac44">Võru maakond</span></p></td><td class="cl-3ac18084"><p class="cl-3ac1611c"><span class="cl-3abcac44">35 782</span></p></td><td class="cl-3ac18085"><p class="cl-3ac1611c"><span class="cl-3abcac44">67</span></p></td><td class="cl-3ac18086"><p class="cl-3ac1611c"><span class="cl-3abcac44">0,0019</span></p></td><td class="cl-3ac1808e"><p class="cl-3ac1611c"><span class="cl-3abcac44">534,1</span></p></td></tr></tbody></table></div>
```

Kui me nüüd tahame arvutada Eesti keskmise sissetuleku lähtuvalt maakondade kaalutud keskmisest, siis peame esmalt maakondade keskmised kaaludega läbi korrutama, kokku liitma ning seejärel kaalude summaga läbi jagama. 

$$\frac{(1531 \times 8926) + (993 \times 140) + ... + (1113 \times 534)}{8926 + 140 + ... + 534} = 1351$$

Märksa lähemal tõelisele Eesti keskmisele sissetulekule. Päris sama summat ei saanud me peamiselt seetõttu, et võtsime kaalumise aluseks rahvaarvu, mitte töötavate inimese arvu. Lisaks on tõenäoline, et sissetulekute jaotused erinevad maakondade lõikes, mis tähendab, et tegelikult ei oleks siinkohal väga õige aritmeetilist keskmist kasutada.


### Post-stratifikatsiooni kaalud
Post-stratifikatsiooni abil saame parandada valimi representatiivsust peale valimi moodustamist. Näiteks juhul kui meie valim on moodustatud aadresside alusel, siis ei saa me planeerida oma valimit vastajate vanuselisest ja soolisest jaotusest lähtuvalt, kuigi üldkogumi kohta on meil need proportsioonid teada. Teine ja märksa levinum põhjus post-stratifikatsiooni jaoks on mitte-vastamine (*non-response*). Mõnede gruppide puhul kipub vastamisaktiivsus olema mõnevõrra madalam (näiteks noored mehed). Ka mitte-vastamise puhul ei ole meil valimi disainimise juures palju teha (võime muidugi suurendada noorte meeste valimisse sattumise tõenäosust, kuid me ei saa kindlustada kogu valimi vastavust üldkogumi proportsioonidele) ja selle ulatust näeme me vaid peale küsitluse läbiviimist.  Kui me siis hiljem avastame, et kuigi mehi peaks olema üldkogumis 50%, on neid valimisse sattunud 40%, siis tähendab see seda, et meie valim ei ole soo lõikes representatiivne. Naised on üleesindatud ja mehed alaesindatud. Sellisel juhul on võimalik välja arvutada post-stratifikatsiooni kaalud. Kaalude moodustamisel peame naisi vähemaks kaaluma $0.5 \div 0.6 \approx 0.8333$ ja mehi rohkemaks kaaluma $0.5 \div 0.4 = 1.25$. Kui valimi kaalud on eelnevalt olemas, siis modifitseerime valimi kaale korrutades iga meessoost respondendi kaalud läbi $1.25$-ga ja iga naissoost respondendi kaalud läbi $0.83$-ga. 

Post-stratifikatsiooni kasutatakse tavaliselt valimi representatiivsuse tõestmiseks erinevate sotsiaaldemograafiliste tunnuste lõikes (sugu, vanus, haridus jne). Kuid kaalude moodustamiseks peame teadma kõikide post-stratifikatsioonitunnuste ristlõigete osakaale. Ehk siis kui tahame post-stratifitseerida hariduse ja soo lõikes, siis peame teadma kõrgharitud meeste osakaalu, kõrgharitud naiste osakaalu, keskharitud meeste osakaalu jne. Tihti taolist ristõikelist üldkogumi jaotust me ei tea. Lisaks võivad nii moodustatud grupid minna väga väikeseks ja tekib oht, et mõnda ristlõiget meil valimis ei olegi. Näiteks kui lisaksime haridusele ja soole veel ka vanuse (näiteks vanused 15-75), siis oleks meil juba $2\times3\times60 = 360$ gruppi. Arvestades tavapärast valimimahtu (*ca* 1000 vaatlust) on ülimalt tõenäoline, et osasid post-stratifikatsiooni ristlõikesid meie valimisse lihtsalt ei sattunud.

#### Raking ja calibration
Miks me ei saa post-stratifikatsioonikaale iga sotsiaaldemograafilise tunnuse lõikes eraldi välja arvutada ja seejärel need erinevad kaalud läbi korrutada? Kui me arvutaksime kõigepealt välja soo kaalud, siis kaalude rakendamisel oleks meie valim soo lõikes representatiivne. Kui me seejärel arvutaks välja hariduse kaalud ja rakendaks ka need, siis oleks meie valim hariduse lõikes representatiivne, kuid soo proportsioonid oleksid jälle paigast ära. Ja kui me siis kasutaks veel ka vanuse kaale, oleks meie valim representatiivne vanuse lõikes, kuid mitte enam soo ega hariduse lõikes. Peaksime nüüd uuesti arvutama soo kaalud, siis uuesti hariduse kaalud ja siis uuesti vanuse kaalud. Ja seejärel jälle otsast peale. Niikaua, kuni oleme leidnud mingisuguse ekviliibriumi, kus ühegi tunnuse kaal enam ei muutu. Taolist iteratiivset protsessi nimetatakse rakinguks (ka *iterative proportional fitting*).  

Alternatiivne viis erinevate tunnuste lõikes valimi proportsioonide korrigeerimiseks on kalibreerimine. Kalibreerimise puhul kasutakse valimi üldkogumiga proportsiooni viimiseks regressioonimudelit, mille abil arvutatakse kalibratsioonikaalud, millega siis korrigeeritakse valimi kaale.  

### Mitte-vastamise kaalud (non-response weights)
Kuigi post-stratifitseerimisega on võimalik neid gruppe, kus vastamismäär oli madalam kui valimiraam ette nägi, üles kaaluda, on tihti otstarbekas pöörata tähelepanu ka otseselt mitte-vastanutele. Kui post-stratifikatsiooni või rakingu/kalibreerimisega üritatakse tasanda eelkõige valimiraami ja üldkogumi erinevusi (juhuvalim, tänu sellele, et see on juhuslik, ei taga alati, et valim vastaks üldkogumi proportsioonidele) terves valimis, siis mitte-vastamise kaalude abil üritatakse tagada, et reaalne valim vastaks teoreetilisele valimile. See tähendab, et üles kaalutakse ainult neid gruppe, kus vastamismäär oli madalam ja gruppe, kus vastamismäär oli 100%, kaale ei muudeta. Tulles tagasi eelneva soolise erinevuse näite juurde: oletame, et meie valimi suuruseks oli 1000 inimest, kellest 50% olid valimi järgi naised ja 50% mehed (valimis vastavalt 500 ja 500), kuid peale küsitlust avastame, et algsest 1000-st respondendist õnnestus küsitleda 500-t naist ja 400-t meest. Ehk siis naiste vastamismäär oli 100% ja meeste vastamismäär 80%. Kuna naiste valimi osaga on kõik korras, ei taha me nende puhul midagi muuta. Küll aga tahame suurendada meeste kaale nii, et meeste valimi osa vastaks algsele valimiraamile. See tähendab, et me peaksime suurendama meeste kaale $500\div400 = 1.25$ võrra. Iga valimisse sattunud meest arvstame seega 1.25 kordselt.  

Teine võimalus mitte-vastamise kaalude arvutamiseks on kasutada logistilist regressiooni, kus valimiraamist lähtuvad sotsiaaldemograafilised tunnused on aluseks hinnangule vastamise ja mitte-vastamise kohta. 

### Kaaludest üldiselt
Ise kaale arvutades peaksime jälgima, et meie arvutatud kaalud liiga suureks ei läheks. See juhtub siis, kui mõni grupp mille lõikes me kaale arvutame, on valimis väga alaesindatud. Näiteks kui tahame tagada, et meie valim vastaks üldkogumile töötuse tunnuse lõikes, kuid valimisse on sattunud töötuid vaid 1%, samas kui üldkogumis on töötuid näiteks 10%. Me peaksime kõik olemasolevad töötud kümnekordselt üles kaaluma. Seda on aga ilmselgelt liiga palju. Me ei taha mõne töötu pealt tehtud järeldusi, mis võivad olla suhteliselt juhuslikud, laiendada küllaltki suurele osale populatsioonist. Seetõttu tuleks pärast kaalude moodustamist alati kontrollida, et need ikka mõistlikkuse piiresse jääks (see mõistlikkuse piir oleneb kontekstist) ja vajadusel suuremaid kaalusid väiksemaks teha (*weight trimming*).

Kui andmestikus on mitu kaalude tunnust, näiteks valimi kaalud ja mitte-vastamise kaalud, siis saame need ühendada üheks kaalu tunnuseks. Selleks peame iga vaatluse jaoks tema kaalud läbi korrutama. Ehk siis kui konkreetse vaatluse jaoks on valimi kaalud väärtusega 0.8 ja mitte-vastamise kaalud 1.2, siis vaatluse lõplikeks kaaludeks kujuneb $0.8 \times1.2 = 0.96$.  


## Valimidisain 
Olukorras, kus kõigil üldkogumi liikmetel ei ole võrdset võimalust valimisse sattuda (kuid kõigil on see võimalus mingi tõenäosusega siiski olemas) või valimi valikuühik ei ole sama mis analüüsiühik (näiteks kui valim on moodustatud leibkondade põhjal aga analüüsime lebkondades olevaid isikuid), on meil tegemist mingi __valimidisaini__ alusel moodustatud valimiga. Valimidisainiga defineeritakse iga analüüsiühiku erinevad valimisse sattumise tõenäosused. Kui me valimi aluseks olevat disaini andmete anlüüsimisel arvesse ei võta, võime analüüsi tulemusel teha väga valesid järeldusi. Seda nii punkthinnangute (nagu eelnevas näites) kui ka standardvigade osas. 

Laias laastus võib erinevad valimidisainid jagada kahte suuremasse gruppi: stratifitseeritud valimid ja klastervalimid. Üldjuhul kasutatakse reaalselt nende kahe tüübi kombinatsioone või variatsioone. Konkreetse uuringu juures kasutatav valimidisain on tavaliselt kirjeldatud uuringu dokumentatsioonis (kui see nii ei ole, siis tasub alati uuringu läbiviijalt seda küsida). Tihti on selle seletuse juures ära toodud ka juhised edasiseks analüüsiks. Seega esimeseks sammuks mingi uuringu kasutamisel peaks alati olema uuringu dokumentatsiooniga tutvumine.

Kuid miks üldse kasutatakse mingeid keerulisi valimidisaine ja ei piirduta tavaliste juhuvalimitega, mida oleks standardmeetoditega lihtne analüüsida? Esimene ja tihti määravaim põhjus on küsitlusega kaasnev kulu. Keerulisemad valimidisainid võimaldavad kontsentreerida küsitluste läbiviimist, lihtsustades seeläbi küsitlusega kaasnevat logistikat. Teine, ja tegelikult mõnevõrra olulisem põhjus on teatud keerulisemate valimidisainidega kaasnev tulemuste kvaliteedi tõus. Me saame valimidisainiga sihtida konkreetseid gruppe või tõsta uuringu üldist täpsusastet.


### Stratifitseeritud juhuvalim
Üldkogum jagatakse teineteist välistavatesse gruppidesse (stratad) ja igas grupis viiakse läbi juhuvalik. Stratifitseeritud valimiga on võimalik tagada, et stratifitseeriva tunnuse lõikes on valim ühtlaselt jaotunud ning vähem varieeruv. Seetõttu on ka selle põhjal tehtavad hinnangu täpsemad (standardvead on väiksemad). 

Tihti tahame teha järeldusi mõne küllaltki marginaalse grupi kohta. Et need järeldused oleksid statistiliselt täpsed, on meil vaja tagada, et see grupp oleks esindatud suuremalt kui see juhuvalikuga võimalik on (mida suurem on uuritava grupi valim, seda täpsemaid hinnanguid me selle kohta teha saame). Näiteks kui tahaksime üle-Eestilises uuringus käsitleda mõnda spetsiifilist küsimust Hiiumaa kohta, siis 1000 inimesega juhuvalimiga satuks meie valimisse 7 hiidldast (Hiiumaa rahvaarv moodustab 0.7% Eesti rahvastikust). Seda on aga liiga vähe et me saaksime Hiiumaa kohta midagi olulist järeldada. Seega peaksime hiidlaste valimisse sattumise tõenäosust mõnevõrra suurendama. 

Lisaks võimaldab stratifitseeritud valim mõningal määral lihtsustada andmekogumise administreerimist (Näiteks igas maakonnas eraldi uuringu läbiviija) või isegi kasutada stratades erinevaid valimi moodustamise meetodeid.  

Stratifitseeritud valim eeldab, et strtifitseerimise aluseks olev tunnus oleks valimi moodustamisel iga üldkogumi liikme jaoks teada. See võib teatud juhtudel aga küllaltki problemaatiline olla. Näiteks kui me tahame stratifitseerida maakonna alusel ja üldkogumi moodustamisel lähtuda rahvastikuregistrist, siis on küllaltki tõenäoline, et rahvastikuregistris märgitud elukoha maakond (kui see seal üldse märgitud on) erineb reaalsest elukoha maakonnast.

### Klastervalim
Klastervalimi puhul käsitletakse analüüsiühikuid mingite klastrite liikmetena ning valimi moodustamisel ei valita mitte analüüsiühikuid otse vaid neist moodustunud klstereid. Juhuvaliku alusel valitakse klastrid ning kõikide valimisse sattunud klastrite liikmeid küsitletakse. Kõige lihtsama näitena võib siinkohal tuua koolivõrgu. Eestis on ca 530 üldhariduskooli. Kui me tahame teha küsitlust, mis oleks representatiivne kõigi Eesti õpetajate suhtes, siis juhuvalimi korral peaksime olema valmis, et kõikidest koolidest satub meie valimisse mõni õpetaja (kuna kõigil õpetajatel on võrdne tõenäosus valimisse sattuda). Kõik koolid läbi käia ja seal paari õpetajat küsitleda oleks logistilisel küllaltki tülikas ning mitte eriti aja- ja kuluefektiivne. Lihtsam, kiirem ja odavam oleks valimi alusena käsitleda koole, teha koolide juhuvalim ning valimisse sattunud koolides küsitleda kõiki õpetajaid. Sellisel juhul oleks meie üldkogum ikkagi kogu Eesti õpetajaskond (kuna kõikidel koolidel ja seeläbi ka kõikidel õpetajatel õpetajatel oli võimalus valimisse sattuda) ja kui me taoliselt moodustatud valimidisaini hiljem analüüsi käigus arvestame, siis saaksime tehtud järeldused üldistada ka kõikidele Eesti õpetajatele.

Võib-olla ei ole isegi mõtet kõiki valimisse sattunud koolide õpetajaid intervjueerida. Me saaksime tegelikult ka igas koolis teha eraldi teise tasandi juhuvalimi ja küsitleda ainult valimisse sattunud õpetajaid. Seega esmalt valime juhuvalimi alusel koolid ja seejärel juhuvalimi alusel õpetajad neis koolides. Taolist valimidisani nimetatakse mitmetasandiliseks klastervalimiks. Neid tasandeid võib olla ka rohkem kui kaks. Näiteks esimene juhuvalik on koolide tasandil, teine klasside tasandil ja kolmas õpilaste tasandil. Esimese tasandi valimiühikuid nimetatakse *primary sampling units* või *PSU* (koolid), teise tasandi ühikuid *secondary sampling units * või *SSU* (klassid) jne. 
 
Võrreldes juhu- või stratifitseeritud valimiga klastervalim sama valimimahu juures üldiselt vähendab hinnangute täpsust, kuna inimesed klastrite sees kipuvad olema sarnasemad kui klastrite vahel. Kuid samas võimaldab klastervalimi kuluefektiivsus koostada suuremaid valimeid, mis omakorda suurendavad täpsust. Seega kokkuvõttes võib mõnevõrra suurema mahuga klastervalimiga saada väiksema mahuga juhuvalimiga võrreldava täpsusastmega hinnagud väiksema raha eest. 

## Tulemuste valimidisaini suhtes korrigeerimine

Punkthinnanguid saame üldjuhul korrigeerida valimi kaaludega. Näiteks kaalutud keskmisi saame ka käsitsi välja arvutada, nagu me eelnevalt tegime, või kasutada selleks vastavaid funktsioone (Ri baasfunktsioon `weighted.mean()` võtab sisendiks kaalumata keskmiste vektori ja kaalude vektori).

Standardvigade korrigeerimine asi mõnevõrra keerulisem ja nende puhul tuleks kasutada spetsiifilisemaid lähenemisi. Eelnevalt vaatasime tavalise juhuvalimi standardvigade arvutamise loogikat (standardviga on valimijaotuse standardhälve, näidates kui suur on meie hinnangu keskmine viga kui me võtaksime samast popultaioonist lõputult valimeid). Keerulisemate valimidisainide puhul juhuvalimi loogika enam ei toimi, kuna vaatlused ei ole omavahel sõltumatud ja/või valiku ühikuks ei ole analüüsiühik. Sellises olukorras on meil tegelikult päris mitmeid võimalusi, kuidas standardvigasid, ehk siis valimijaotuse varieeruvust, hinnata. Peamisteks kasutatavateks meetoditeks on:

- Taylori seeriate meetod (*Taylor series linearisation*)
- Bootstrapi replikatsiooni meetod
- Jackknife replikatsiooni meetod
- BRR (*balanced repeated replication*)

Kui Taylori seeriate meetodi puhul arvutatakse standardvead analüütiliselt, siis ülejäänud replikatsioonipõhiste meetodite puhul empiiriliselt. Üldiselt ei pea nende meetodite hingeelu nende kasutamiseks väga põhjalikult tundma (vaatame siiski replikatsioonimeetodeid, kuna nende loogika on küllaltki lihtne).

### Replikatsioonikaalud (replicate weights)
Keerulisemate valimidisainide ja mitte-lineaarsete meetoodite puhul ei ole alati võimalik standardvigasid analüütiliste meetoditega arvutada. Sel juhul on standardvigade leidmisks võimalik  kasutada erinevad replikatsioonimeetodid, nagu *bootstrap* või *jackknife* (reaalsuses küll tavaliselt mõnda nende variatsioonidest). Paljude suuremate uuringute puhul on andmestikuga kaasas replikatsioonikaalud, mis võimaldavad replikatsioonimeetodeid kasutada. Näiteks OECD uuringutes nagu PISA või PIIAC. Replikatsioonimeetodeid võib ja saab kasutada ka tavalise juhuvalimi korral. Ajalooliselt on nende laiem kasutus jäänud arvutusvõimsuste taha, kuid tänapäeval, kui see enam probleem ei ole, on need järjest rohkem hakanud tavapäraseid analüütilisi standardvigade arvutamise meetodeid asendama.

Kõikide replikatsioonimeetodite üldprintsiip ja loogika on lihtne. Olemasolevast valimist võetakse palju alamvalimeid (replikatsioone), ehk siis valimit käsitletakse üldpopultaioonina, millest võetkse omakorda valimid. Kõikide alamvalimite puhul arvutatakse huvipakkuv statistik (näiteks mingi tunnuse keskmine). Alamvalimite statistikutest moodustub (pseudo)valimijaotus, mille standardhälve ongi standardviga. Seega kui tavaline standardvea arvutamise metoodika lähtub küll potentsiaalsest eeldusest, et valimijaotuse aluseks olevaid valimeid on lõputult, kuid tuletab standardvea analüütiliselt ($se = \frac{sd}{\sqrt{n}}$), siis replikatsioonimeetodid tuletavad olemasolevast valimist suurel hulgal alamvalimeid, mille alusel moodustavad valimijaotuse ja tuletavad standardvea empiiriliselt.

Repikatsioonimeetodid erinevad üksteisest selle poolest kuidas nad neid alavalimeid moodustavad. *Bootstrap* meetodiga võetakse üldvalimist juhuslikkuse alusel sama palju vaatlusi kui seal algselt oli, kuid kasutatakse nn tagasipaneku meetodit. See tähendab, et mõni algse valimi vaatlus võib alamvalimisse sattuda mitu korda ja mõni üldse mitte. Kui palju alamvalimeid võetakse, on analüütiku otsustada (mida rohkem, seda parem, kuid võiks olla vähemalt 100).

*Jackknife* meetodiga võetakse alamvalimeid nii palju kui algses valimis vaatlusi oli. Kuid iga alamvalimi puhul jäetakse mingi reegli alusel üks vaatlustest välja. Ülejäänud vaatlused korrutatakse läbi koefitsiendiga, mis korrigeerib alamvalimi suuruse võrdseks algse valimiga. Näiteks kui algses valimis oli 10 inimest, siis võetakse 10 alamvalimit, milles kõigis on 9 inimest ja Kõik alavalimid korrutatakse läbi 1.1-ga ($\frac{10}{9}$)

Replikatsioonikaalud annavad meile info kuidas valimite replikeerimine peaks toimuma.


## Küsitlusandmed Ris

Ris on küsitlusandmete analüüsiks spetsiaalne pakett *survey*, mis võimaldab kasutada erinevaid analüüsimeetodeid arvestades samal ajal ka valimidisainist tulenevate eripäradega. Kuna praktiliselt kõik suuremad küsitlused kasutavad mingeid keerukamaid valimidisaine, siis peame nende andmete analüüsimisel alati ka vastavate disainidega arvestama ega saa kasutada tavapäraseid meetodeid.

Kõigepealt installige (kui te seda juba teinud ei ole) *survey* pakett ja lugege see sisse. Nagu alati, siis installima peab paketi ainult ühe korra, kuid igaks sessiooniks tuleb see uuesti sisse lugeda. *survey* paketiga on kaasas ka näidisanmdestikud. Lugege ka need sisse (´data(api)´). *api* andmestikuga on mõõdetud akadeemilise võimekuse indeksit kõikides Kalifornia koolides. Andmestiku analüüsiühikuks on kool ehk siis andmestik koondab koolitsandi infot. 


```r
#install.packages('survey')
library(survey)
data(api)
```

*survey* paketis peab kõigepealt defineerima valimidisaini, milles kirjeldatakse kõiki valimi moodustamise eripärasid, kaale jne. Disaini defineerimise läbi koondatakse kogu valimidisainist lähtuv info ühte andmeojekti. Disaini deineerimiseks on funktsioon `svydesign()`:

### Kaaludega tavalise juhuvalimi defineerimine

Valimidisain tavalise juhuvalimi puhul kui meile on ainult valimi kaalud ja/või mingid muud kaalud. Isegi tavalise juhuvalimi puhul peaksime ikkagi kasutama vähemalt valimi kaale (need lubavad meil hinnata näiteks populatsiooni suurust). Lisaks valimi kaaludele või valimi kaalude asemel võivad andmestikus olla ka mitte-vastamise kaalud või poststratifikatsiooni kaalud (või oleme need ise välja arvutanud), mille olemasolu või vajadus ei sõltu sellest, kas tegemist on tavalise juhuvalimiga või keerulisema disainiga. Kui andmestikus on mitu kaalude tunnust, mida meil on vaja kasutada, siis peaksime need omavahel läbi korrutades üheks tunnuseks koondama. 

`svydesign()` funktsiooni argumentidena peame defineerima:  

- `ids` argumendiga defineeritakse valimiühikud (*PSU*). Need on klastri id'd klastervalimi puhul, ehk siis tunnus, mille lõikes klastervalimi valik toimus. Kui valik toimus analüüsitasandil ilma klastriteta, siis tuleks märkida `ids = ~1`
- `weights` tähistab kaalu tunnust. Tunnuse nime ette tuleb kindlasti panna tilde märk (või viidata tunnusele otse apisrs$pw)
- `data` on meie algne küsitlusandmestik


```r
# Kasutame andmestikku apisrs
# kaalude tunnus on 'pw'
des_jv = svydesign(ids = ~1, 
                   weights = ~pw, 
                   data = apisrs)
```

Väiksemate üldkogumite korral, kui me teame üldkogumi suurust, saab kasutada lõpliku populatsiooni korrektsiooni (*finite population correction* ehk *fpc*), mis võimaldab kasutada mõnevõrra väiksemaid standardvigasid. Kui üldkogum on väike, siis on ka valim üldkogumile pigem sarnasem, võrreldes juhuga kui üldkogum on väga suur. Seega on valimis ka vähem määramatust ning standardvead väiksemad.

*fpc* defineeritakse parameetriga:

- `fpc` mille kaudu peab defineerima tunnuse, mis sisaldab iga vaatluse kohta üldkogumi suurust. Tavalise juhuvalimi puhul on see suurus kõikide vaatuste jaoks sama.


```r
des_jv = svydesign(ids = ~1, 
                   weights = ~pw, 
                   fpc = ~fpc, 
                   data = apisrs)
```

Küsitluse disainist ülevaate saamiseks saame kasutada `summary()` funktsiooni:

```r
summary(des_jv)
```

```
## Independent Sampling design
## svydesign(ids = ~1, weights = ~pw, fpc = ~fpc, data = apisrs)
## Probabilities:
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
## 0.03229 0.03229 0.03229 0.03229 0.03229 0.03229 
## Population size (PSUs): 6194 
## Data variables:
##  [1] "cds"      "stype"    "name"     "sname"    "snum"     "dname"   
##  [7] "dnum"     "cname"    "cnum"     "flag"     "pcttest"  "api00"   
## [13] "api99"    "target"   "growth"   "sch.wide" "comp.imp" "both"    
## [19] "awards"   "meals"    "ell"      "yr.rnd"   "mobility" "acs.k3"  
## [25] "acs.46"   "acs.core" "pct.resp" "not.hsg"  "hsg"      "some.col"
## [31] "col.grad" "grad.sch" "avg.ed"   "full"     "emer"     "enroll"  
## [37] "api.stu"  "pw"       "fpc"
```

### Stratifitseeritud valimi defineerimine
Stratifitseeritud valimi puhul tuleb meil defineerida stratifitseeriv tunnus. Andmestikus *apistrat* on selleks *stype* (koolitüüp) tunnus, mille lõikes koolid on stratifitseeritud.  

- `strata` argumendiga defineeritakse valimit stratifitseeriv tunnus
- `fpc` argumendiga saab määrata iga strata suuruse (kui see on olemas, siis ole vaja valimi (disaini) kaale eraldi märkida, survey arvutab vaatluste valimisse sattumise tõenäosused ja kaalud ise välja)


```r
des_strat = svydesign(ids = ~1, 
                      strata = ~stype,
                      weights = ~pw, 
                      fpc = ~fpc, 
                      data = apistrat)
```

### Ühetasandilise klastervalimi defineerimine

Kasutame *apiclus1* andmestikku, milles on koolid klasterdatud piirkonna (*dnum*) järgi. Ehk siis piirkonnad on esimese tasandi valikuks. Valimisse sattunud piirkondade kõik koolid on valimisse kaasatud. 

- `ids` argumeniga defineeritakse *PSU* ehk klastri id (*dnum*)
- `weights` argumendiga määratakse valimi kaalud. Jällegi, kui tegemist on ainult valimi kaaludega ja `fpc` on defineeritud, siis ei pea kaale määrama (*survey* arvutab need ise välja)
- `fpc` valimi suurus (klastrite koguarv) 


```r
des_clus <- svydesign(ids=~dnum, 
                      weights=~pw, 
                      data=apiclus1, 
                      fpc=~fpc)
```

### Mitmetasandilise klastervalimi defineerimine

Andmestikuks on *apiclus2*, kus esimese tasandina (*PSU*) on valitud kooli piirkonnad ja teise tasandina (*SSU*) koolid. Ehk kõigepealt on tehtud piirkondade valim ja seejärel igas valimisse sattunud piirkonnas omakorda koolide valim.

- `ids` argumeniga on defineeritud PSU ja SSU id'd
- `fpc` argumendiga on defineeritud PSU ja SSU üldkogumite suurused (vastavalt piirkondade koguarv ja koolide koguarv piirkonnas)


```r
des_clus2 <- svydesign(ids=~dnum+snum, 
                       fpc=~fpc1+fpc2, 
                       data=apiclus2)
```

### Replikatsioonikaaludega valimi defineerimine

Replikatsioonikaalude tegemiseks on *survey* funktsioon `as.svrepdesign()`, mis võtab sisendiks olemasoleva ilma replikatsioonikaaludeta disainiobjekti ja annab väljundiks kaaludega disainiobjekti.

- `design` argumendiga defineeritakse survey disain, millele tahetakse replikatsioonikaale arvutada
- `type` argumendiga defineeritakse replikatsioonimeetodi tüüp. Variandid on "auto", "JK1", "JKn", "BRR", "bootstrap", "subbootstrap","mrbbootstrap","Fay". Täpsemalt on ndende kohta võimalik lugeda funktsiooni abifailist: `?as.svrepdesign`


```r
# Defineerime kõigepealt survey disaini 
des_clus <- svydesign(ids=~dnum, 
                      weights=~pw, 
                      data=apiclus1)
# Arvutame kaalud
rw1<-as.svrepdesign(design = des_clus,
                    type = 'JK1')
```

Replikatsioonikaalude kasutamiseks, juhul kui me ise neid kaale ei arvuta ja need on meie andmestikkus juba olemas, peame defineerima jällegi vastava survey disainiobjekti. Näidisandmestikes ühtegi replikatsioonikaaludega andmestikku ei ole. Kuid saame selle vähese vaevaga eelneva näite replikatsioonikaalude objekti abil teha:


```r
indeks <- data.frame(indeks = rw1$repweights$index)
kaalud <- as.data.frame(rw1$repweights$weights)
names(kaalud) <- paste0('rep_w_', 1:15)
kaalud$indeks <- 1:15
kaalud <- left_join(indeks, kaalud, by = 'indeks')
apiclus_rep = cbind(apiclus1, kaalud)
```

Kui kaaludega andmestik on olemas, siis saame replikatsioonikaalude disaini defineerida funktsiooniga `svrepdesign()`. Funktsioonis on kindlasti vaja defineerida järgmised argumendid:

- `repweights` argumendiga defineeritakse replikatsioonikaalud. Neid kaale on tavaliselt küllaltki palju. Seega on otstarbekas need enne andmestikust välja võtta. Näiteks *dplyr* paketi `select()` funktsiooniga. Kuna tavaliselt on kaalud mingi kindla reegli alusel nimetatud, siis on mugav kasutada `starts_with()` funktsiooni, mis võimaldab valida kõik ühtse nimeosaga tunnused.
- `type` argumendiga määratakse replikatsioonikaalude tüüp. Võimalikud tüübid on "BRR","Fay","JK1", "JKn","bootstrap","ACS","successive-difference","JK2" ja "other". See, millist tüüpi on vaja kasutada, peaks olema kirjas küsitluse dokumentatsioonis. Näiteks PISA uuringus on kasutatud "Fay" meetodit.
- `data` argumendiga defineeritakse küsitluse andmestik.
- `combined.weights` argument ütleb, kas valimi kaalud on juba liidetud replikatsioonikaaludele. Tvaliselt see nii ongi (ja `combined.weights` vaikimisi väärtus on T), kuid meie isetehtud andmestikus ei ole.



```r
library(dplyr)
kaalud <- apiclus_rep %>% 
  select(starts_with('rep_w_'))

des_rw <- svrepdesign(repweights = kaalud,
                      weights = ~pw,
                      type = 'JK1',
                      data = apiclus_rep,
                      combined.weights = F)
```

## Valimiandmete analüüs

Kui valimidisain on defineeritud, siis saab seda kasutada edasistes analüüsides. Selleks on terve hulk *survey* funktsioone, mis kõik algavd *svy* eeliitega. Tasub meeles pidada, et *survey* diainiobjektid sobivad sisendina ainult *survey* funktsioonidele (mõne erandiga). Näiteks tavalise lineaarse regressiooni `lm()` funktsiooni kasutada ei saa (küll aga *survey* `glm()` funktsiooni, mis võimaldab meil samuti lineaarset regressiooni jooksutada). Silmas tasub pidada ka seda, et enamke funktsioonide puhul on vaja kasutada tilde märki. 

**Üldkogumi kogusumma:**


```r
# Mitu õpilast õpib Kalifornia koolides (enroll tunnus)
svytotal(~enroll, design = des_clus)
```

```
##          total     SE
## enroll 3404940 941611
```

**Tunnuse keskmine:**


```r
# Akadeemilise võimekuse indeksi (tunnus api00) keskmine 
svymean(~api00, design = des_clus)
```

```
##         mean     SE
## api00 644.17 23.779
```

Kui tahame keskmisele **usalduspiire**, siis saame kasutada funktsiooni `confint()`:


```r
mod <- svymean(~api00, design = des_clus)
confint(mod)
```

```
##          2.5 %   97.5 %
## api00 597.5634 690.7754
```

Võime ka korraga mitme tunnuse keskmist hinnata:


```r
svymean(~api00+api99, design = des_clus)
```

```
##         mean     SE
## api00 644.17 23.779
## api99 606.98 24.469
```

Saame ka **kategoriaalsete tunnuste proportsioone** hinnata: 


```r
svymean(~stype, design = des_clus)
```

```
##            mean     SE
## stypeE 0.786885 0.0468
## stypeH 0.076503 0.0271
## stypeM 0.136612 0.0299
```

**Kvantiilid:**


```r
# vajalikud kvantiilid defineerime vektorina
svyquantile(~api00, 
            design = des_clus, 
            quantiles = c(.25,.5,.75))
```

```
## $api00
##      quantile ci.2.5 ci.97.5       se
## 0.25      552    491     628 31.93791
## 0.5       652    559     715 36.36725
## 0.75      719    696     777 18.88300
## 
## attr(,"hasci")
## [1] TRUE
## attr(,"class")
## [1] "newsvyquantile"
```

**Gruppide kaupa hinnagud:**


```r
svyby(~api00, 
      by = ~stype, 
      design = des_clus, 
      FUN = svymean)
```

```
##   stype    api00       se
## E     E 648.8681 22.58731
## H     H 618.5714 38.40263
## M     M 631.4400 31.92737
```

Saame hinnata ka mitut tunnust mitme grupi lõikes:


```r
svyby(~api00+api99, 
      by = ~stype+sch.wide, 
      design = des_clus, 
      FUN = svymean)
```

```
##       stype sch.wide    api00    api99 se.api00 se.api99
## E.No      E       No 596.3333 601.6667 43.92749 47.75128
## H.No      H       No 659.3333 662.0000 27.27433 29.52400
## M.No      M       No 606.3750 611.3750 41.53039 41.53240
## E.Yes     E      Yes 653.6439 608.3485 20.52153 21.74141
## H.Yes     H      Yes 607.4545 577.6364 44.14423 46.96892
## M.Yes     M      Yes 643.2353 607.2941 42.55219 42.95820
```

Kui on vaja usalduspiire:


```r
svyby(~api00+api99, by = ~stype+sch.wide, design = des_clus, FUN = svymean, vartype = 'ci')
```

```
##       stype sch.wide    api00    api99 ci_l.api00 ci_l.api99 ci_u.api00
## E.No      E       No 596.3333 601.6667   510.2370   508.0759   682.4296
## H.No      H       No 659.3333 662.0000   605.8766   604.1340   712.7900
## M.No      M       No 606.3750 611.3750   524.9769   529.9730   687.7731
## E.Yes     E      Yes 653.6439 608.3485   613.4225   565.7361   693.8654
## H.Yes     H      Yes 607.4545 577.6364   520.9334   485.5790   693.9756
## M.Yes     M      Yes 643.2353 607.2941   559.8345   523.0976   726.6361
##       ci_u.api99
## E.No    695.2575
## H.No    719.8660
## M.No    692.7770
## E.Yes   650.9609
## H.Yes   669.6938
## M.Yes   691.4906
```

Regressioonimudelite jaoks on funktsioon `svyglm()`, mis on väga sarnane `glm()` funktsioonile.

**Tavaline lineaarne regressioon:**


```r
# Lineaarse regressiooni jaoks defineerime argumendi family = gaussian(). 
# See on tegelikult ka vaikimis väärtus 
#  ja me ei pea seda ilmtingimata märkima
mod <- svyglm(api00 ~ ell + meals + mobility, 
              design = des_clus, 
              family = gaussian())
summary(mod)
```

```
## 
## Call:
## svyglm(formula = api00 ~ ell + meals + mobility, design = des_clus, 
##     family = gaussian())
## 
## Survey design:
## svydesign(ids = ~dnum, weights = ~pw, data = apiclus1)
## 
## Coefficients:
##             Estimate Std. Error t value Pr(>|t|)    
## (Intercept) 819.2791    21.6051  37.921 5.18e-13 ***
## ell          -0.5167     0.3273  -1.579    0.143    
## meals        -3.1232     0.2809 -11.119 2.54e-07 ***
## mobility     -0.1689     0.4494  -0.376    0.714    
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## (Dispersion parameter for gaussian family taken to be 3157.85)
## 
## Number of Fisher Scoring iterations: 2
```

**Logistiline regressioon:**


```r
# family = binomial()
# tunnus awards on kategooriatega "Yes" ja "No". 
# I(awards == 'Yes') käsu abil muudame kõik Yes'id TRUE'ks 
#  ja ülejäänud väärtused FALSE'ik
mod <- svyglm(I(awards == 'Yes') ~ ell + meals + mobility, 
              design = des_clus, 
              family = binomial())
summary(mod)
```

```
## 
## Call:
## svyglm(formula = I(awards == "Yes") ~ ell + meals + mobility, 
##     design = des_clus, family = binomial())
## 
## Survey design:
## svydesign(ids = ~dnum, weights = ~pw, data = apiclus1)
## 
## Coefficients:
##              Estimate Std. Error t value Pr(>|t|)  
## (Intercept)  0.425949   0.351961   1.210   0.2516  
## ell          0.041120   0.015248   2.697   0.0208 *
## meals       -0.014643   0.007044  -2.079   0.0618 .
## mobility     0.007534   0.013571   0.555   0.5899  
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## (Dispersion parameter for binomial family taken to be 0.9907103)
## 
## Number of Fisher Scoring iterations: 4
```


## Plausible values

*Plausible values* või eesti keeles siis ehk usutavad väärtused ei ole tegelikult otseselt küsitlusuuringute teema selles mõttes, et need ei ole seotud valimidisainiga. Küll aga kasutatakse neid küsitlusuuringutes (näiteks PIAACi ja PISA uuringutes), seega on asjakohane neid siin ka põgusalt käsitleda. PIAACi uuringu eesmärgiks on mõõta täiskasvanute oskusi (lugemis-, arvutamis- ja probleemilahendusoskused). Kui me aga vaatame PIAACi andmefaili, siis näeme seal ei ole iga mõõdetava oskuse kohta ühte tunnust, vaid tervelt 10 erinevat tunnust. Need 10 tunnust iga oskuse kohta on nende oskuste usutavad väärtused. Need väärtused on tuletatud iga inimese jaoks lähtuvalt selle inimese vastustest oskusi mõõtvatele küsimustele. Iga inimese jaoks kontrueeritakse tema oskuse tõenäosusjaotus (selleks kasutatakse IRT (*Item Response Theory*) meetodeid). Seejärel võetakse sellest jaotusest 10 juhuslikku väärtus, mis ongi selle inimese usutavad väärtused. 
Kui me tahame nüüd teada, et kas meeste või naiste lugemisoskus on keskmiselt parem, siis mida me tegema peaksime? Me ei tohiks kindlasti arvutada iga inimese jaoks tema usutavate väärtuste keskmist. Samuti ei tohiks me kasutada ainult ühte usutavat väärtust. Mõlemal juhul oleks meie järeldused valed.  
Et saada korrektseid tulemusi, peaksime võrdlema esimese usutava väärtuse tulemusi meeste ja naiste vahel, seejärel võrdlema teise usutava väärtuse tulemusi meeste ja naiste vahel ja nii kümme korda. Seejärel peaksime arvutama kõikide kümne meeste ja naiste erinevuse keskmise, mis olekski korrektne meeste ja naiste erinevus.  
Tundub päris aeganõudev ja tüütu. Õnneks on ka lihtsam viis - kasutada jällegi Ri *survey* paketti (koos *mitools* paketiga):


```r
# Kõigepealt vajalikud paketid. 
# Kui teil neid installitud ei ole, siis tehke seda
library(haven)
library(survey)
library(mitools)
library(stringr)
```


```r
# tõmbame OECD lehelt Piaaci Eesti andmestiku (SPSS faili)
# Selle koodiga tõmbame nad kodukataloogi alamkataloogi "./andmed"
# Võite alati ka otse OECD lehele minna ja andmestiku sealt tõmmata
dir.create("data")
download.file("https://webfs.oecd.org/piaac/puf-data/SPSS/prgestp1.sav", 
              "./data/prgestp1.sav", method="auto", mode="wb")
```



```r
# Loeme andmed sisse
dat <- as.data.frame(read_spss('./data/prgestp1.sav'))

# PIAACI andmestikus on kasutatud replikatsioonikaale
# Otsime kaalude nimed välja 
# Kasutame selleks stringr paketi funktsiooni str_subset
# Kõigepealt valimi kaal
mw <- str_subset(names(dat), "^SPFWT0$")
# Seejärel replikatsioonikaalud
rw <- str_subset(names(dat), "^SPFWT[1-9][0-9]*$")

# Otsime välja ka oskuste usutavate väärtusete tunnused
lit <- str_subset(names(dat), "^PVLIT[0-9]+")
num <- str_subset(names(dat), "^PVNUM[0-9]+")
prob <- str_subset(names(dat), "^PVPSL[0-9]+")

# Loome survey disaini
des_piaac <- svrepdesign(repweights=dat[,rw],
                   weights=dat[,mw], type="JK2", data = dat)
```


```r
f <- as.formula(paste0('lit~', paste(lit, collapse = '+')))
results_list<-withPV(
    mapping = f,
    data = des_piaac,
    action = quote(svyby(~lit, by = ~GENDER_R, design = des_piaac, FUN = svymean, na.rm = T)))

summary(MIcombine(results_list))
```

```
## Multiple imputation results:
##       withPV.svyrep.design(mapping = f, data = des_piaac, action = quote(svyby(~lit, 
##     by = ~GENDER_R, design = des_piaac, FUN = svymean, na.rm = T)))
##       MIcombine.default(results_list)
##    results        se   (lower   upper) missInfo
## 1 275.0582 1.0832068 272.8910 277.2254     41 %
## 2 276.6413 0.8109968 275.0258 278.2569     36 %
```




```r
# Hindame regressioonimudeliga soo mõju lugemisoskusele
# Tulemus peaks olema sama, mis eelmises analüüsis
f <- as.formula(paste0('lit~', paste(lit, collapse = '+')))
results_list<-withPV(
    mapping = f,
    data = des_piaac,
    action = quote(svyglm(lit~as.factor(GENDER_R), design = des_piaac, family = gaussian())))

summary(MIcombine(results_list))
```

```
## Multiple imputation results:
##       withPV.svyrep.design(mapping = f, data = des_piaac, action = quote(svyglm(lit ~ 
##     as.factor(GENDER_R), design = des_piaac, family = gaussian())))
##       MIcombine.default(results_list)
##                         results       se      (lower     upper) missInfo
## (Intercept)          275.058207 1.083207 272.8909806 277.225433     41 %
## as.factor(GENDER_R)2   1.583098 1.243243  -0.8602807   4.026478     15 %
```



