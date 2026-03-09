# 🚗 Calculator Leasing Auto · BT Leasing

Calculator interactiv pentru leasing auto în euro, destinat persoanelor juridice, bazat pe oferta **BT Leasing România**.

🔗 **Live demo:** [tmdroid.github.io/bt-leasing](https://tmdroid.github.io/bt-leasing)

---

## Features

- **EURIBOR 6M live** — se descarcă automat din API-ul public al Băncii Centrale Europene la fiecare accesare, fără cheie API
- **Ofertă promo vs. standard** — comută între marjă 2,30% și 2,45%
- **Parametri ajustabili** — valoare mașină, avans (10–80%), valoare reziduală (0% – max avans), durată (12–60 luni)
- **Calcul pe sold descrescător** — principal fix + dobândă pe soldul rămas, exact cum calculează BT
- **Grafic complet de rambursare** — toate ratele lună cu lună, cu dobânda și comisionul detaliat
- **Design conform brand BT** — culori oficiale (#FFD100, #003DA5, #CC0000), scut tricolor SVG, bandă tricolor

---

## Cum funcționează calculul

Dobânda totală anuală = **Marjă fixă + EURIBOR 6M**

| Ofertă | Marjă | EURIBOR (live) | Total/an* |
|--------|-------|----------------|-----------|
| Promo "Babe fără drame" | 2,30% | ~2,14% | ~4,44% |
| Standard | 2,45% | ~2,14% | ~4,59% |

*valoare orientativă, se actualizează cu EURIBOR

**Rata lunară** = Principal + Dobândă pe sold + Comision gestiune (0,04% + TVA)

**Costuri unice** incluse în estimare:
- Taxă administrare contract: 1,5% (promo) / 2,5% (standard) + TVA
- Taxă servicii logistice: 950 lei + TVA
- Comision evaluare bun rulat: 70€ + TVA (doar pentru mașini second-hand)

---

## EURIBOR API

Datele se preiau din API-ul public al BCE, fără autentificare:
```
https://data-api.ecb.europa.eu/service/data/FM/M.U2.EUR.RT.MM.EURIBOR6MD_.HSTA
  ?lastNObservations=1&format=csvdata&detail=dataonly
```

Dacă fetch-ul eșuează (offline), calculatorul folosește o valoare cached ca fallback.

---

## Utilizare

Fișier HTML standalone — nu are dependențe externe, nu necesită build. Deschide direct în browser sau hostează pe orice server static.

---

## Disclaimer

Calculator **estimativ**, neafiliat oficial cu BT Leasing sau Banca Transilvania. Valorile exacte se stabilesc cu un consultant BT. Oferta promo "Babe fără drame" este valabilă până pe **31 martie 2026**.
