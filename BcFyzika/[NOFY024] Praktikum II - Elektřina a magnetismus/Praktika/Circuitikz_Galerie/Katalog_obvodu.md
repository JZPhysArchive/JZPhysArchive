# Katalog obvodů -- Praktikum II

Tento katalog obsahuje zdrojové kódy a zkompilovaná PDF schémat vytvořených v balíčku `circuitikz`.

## [NOFY024] Úloha V

### Měření napětí na sekundárním vinutí transformátoru

**Zkompilované PDF:** [[NOFY024]_Úloha_V_schema_1.pdf]([NOFY024]_Úloha_V_schema_1.pdf)

```latex
\begin{circuitikz}[]

        \draw (0,-1.1) -- (0,-0.8) to [sV, o-o] (0,0.7) -- (0,1) -- ++(0.5,0)
        node[transformer core, circuitikz/inductors/coils=10,circuitikz/inductors/width=1.25,anchor=A1](T){};
        \draw (T.A2) -- ++ (-0.5,0);
        \draw (T.B1) --  (4,1);
        \draw (3,1) to [rmeter, t=V,*-*] (3,-1.1);
        \ctikzset{bipoles/oscope/width=2.4}\ctikzset{bipoles/oscope/height=1.4}
        \draw (4,1) ++ (0.75,0) ++ (0,-1.5) ++ (1.5,0) node[oscopeshape, anchor =in 1](O){};
        \draw  (O.in 1) ++ (-0.5,0) node[bnc, anchor=zero, rotate=-180](bnc1){};
        \draw  (O.in 1) ++ (-0.5,0) node[right]{\,CH1};
        \draw  (O.in 2) ++ (0.5,0) node[bnc, anchor=zero](bnc2){};
        \draw  (O.in 2) ++ (0.5,0) node[left]{CH2\,};
        \draw (bnc1.hot) -- (4.75,-0.5) -- (4.75,1) -- (4,1);
        \draw (bnc1.shield) ++ (0,-0.28) --++ (0,-0.45) to node[circ](x1){} ++ (0,0);
        \draw (bnc2.shield) --++ (0,-0.45) to node[circ](x3){} (x1);
        \draw (x1) -- (T.B2);
        \draw (x3) to node[ground]{} ++ (0,0);
    
\end{circuitikz}
```

### Jednocestný usměrňovač

**Zkompilované PDF:** [[NOFY024]_Úloha_V_schema_2.pdf]([NOFY024]_Úloha_V_schema_2.pdf)

```latex
\begin{circuitikz}[]

        \draw (0,-1.1) -- (0,-0.8) to [sV, o-o] (0,0.7) -- (0,1) -- ++(0.5,0)
        node[transformer core, circuitikz/inductors/coils=10,circuitikz/inductors/width=1.25,anchor=A1](T){};
        \draw (T.A2) -- ++ (-0.5,0);
        \draw (T.B1) -- (3,1) to [Do] (6,1) to [european resistor, l=\(R_z\), i=\(i\), *-*] (6,-1.1) -- (T.B2); 
        \draw (2.5,-1.2) to [open, v=\(U\)] (2.5,+1.1);
        \draw (6,-1.1) -- (7,-1.1) to [open, v=\(u\), o-o] (7,1) -- (6,1); 
    
\end{circuitikz}
```

### Filtrace napětí na jednocestném usměrňovači

**Zkompilované PDF:** [[NOFY024]_Úloha_V_schema_3.pdf]([NOFY024]_Úloha_V_schema_3.pdf)

```latex
\begin{circuitikz}[]

        \draw (0,-1.1) -- (0,-0.8) to [sV, o-o] (0,0.7) -- (0,1) -- ++(0.5,0)
        node[transformer core, circuitikz/inductors/coils=10,circuitikz/inductors/width=1.25,anchor=A1](T){};
        \draw (T.A2) -- ++ (-0.5,0);
        \draw (2.5,-1.2) to [open, v=\(U\)] (2.5,+1.1);
        \draw (T.B1) -- (3,1) to [Do] (5,1) to [european resistor, l=\(R_{\text{ochr.}}\)] (7,1) to [rmeter, t=A] (9,1) -- (10.5,1);
        \draw (7,1) to [C, l_=\(C\),*-*] (7,-1.1);
        \draw (9,1) to [european resistor, l_=\(R_{z}\),*-*] (9,-1.1);
        \draw (10,1) to [rmeter, t=V,*-*] (10,-1.1);
        \ctikzset{bipoles/oscope/width=2.4}\ctikzset{bipoles/oscope/height=1.4}
        \draw (10,1) ++ (0.75,0) ++ (0,-1.5) ++ (1.5,0) node[oscopeshape, anchor =in 1](O){};
        \draw  (O.in 1) ++ (-0.5,0) node[bnc, anchor=zero, rotate=-180](bnc1){};
        \draw  (O.in 1) ++ (-0.5,0) node[right]{\,CH1};
        \draw  (O.in 2) ++ (0.5,0) node[bnc, anchor=zero](bnc2){};
        \draw  (O.in 2) ++ (0.5,0) node[left]{CH2\,};
        \draw (bnc1.hot) -- (10.75,-0.5) -- (10.75,1) -- (10,1);
        \draw (bnc1.shield) ++ (0,-0.28) --++ (0,-0.45) to node[circ](x1){} ++ (0,0);
        \draw (bnc2.shield) --++ (0,-0.45) to node[circ](x3){} (x1);
        \draw (x1) -- (T.B2);
        \draw (x3) to node[ground]{} ++ (0,0);
    
\end{circuitikz}
```

### Zapojení pro zobrazení voltampérové charakteristiky Zenerovy diody

**Zkompilované PDF:** [[NOFY024]_Úloha_V_schema_4.pdf]([NOFY024]_Úloha_V_schema_4.pdf)

```latex
\begin{circuitikz}[]

        \draw (0,-1.1) -- (0,-0.8) to [sV, o-o] (0,0.7) -- (0,1) -- ++(0.5,0)
        node[transformer core, circuitikz/inductors/coils=10,circuitikz/inductors/width=1.25,anchor=A1](T){};
        \draw (T.A2) -- ++ (-0.5,0);
        \draw (T.B1) -- (3,1) to [european potentiometer, wiper pos = 0.3 ,-*, name=pot] (3,-1.1);
        \draw node[right] at (3.25,-0.5){{{{\rotatebox[origin=c]{90}{\(\SI{100}{\ohm}\)}}}}};
        \ctikzset{bipoles/oscope/width=2.4}\ctikzset{bipoles/oscope/height=1.4}
        \draw (9,1) ++ (0.75,0) ++ (0,-1.5) ++ (1.5,0) node[oscopeshape, anchor =in 1](O){};
        \draw  (O.in 1) ++ (-0.5,0) node[bnc, anchor=zero, rotate=-180](bnc1){};
        \draw  (O.in 1) ++ (-0.5,0) node[right]{\,CH1};
        \draw  (O.in 2) ++ (0.5,0) node[bnc, anchor=zero](bnc2){};
        \draw  (O.in 2) ++ (0.5,0) node[left]{CH2\,};
        \draw (bnc1.hot) to [crossing] ++ (-2.72,0) to [crossing] ++ (-0.27,0) --++ (-3.03,0) --++ (0,-0.6);
        \draw (bnc1.shield) ++ (0,-0.28) --++ (0,-0.45) to node[circ](x1){} ++ (0,0);
        \draw (bnc2.shield) --++ (0,-0.45) to node[circ](x3){} (x1);
        \draw (x3) to node[ground]{} ++ (0,0);
        \draw (x1) --++ (-1.5,0) to node[circ](y){} ++ (0,0);
        \draw (pot.wiper) --++ (0,1.5) --++ (10.5,0) --++ (0,-2.175) -- (bnc2.hot);
        \draw (y) --++ (0,0.5) to [C=\(C\), -*] ++ (0,2.25);
        \draw (y) --++ (-1.5,0) --++ (0,0.5) to [european resistor, l={{{{\rotatebox[origin=c]{90}{\(\SI{100}{\ohm}\)}}}}}, -*] ++ (0,2.25);
        \draw (T.B2) --++ (2,0) to [zDo, *-*] ++ (3.15,0);
        \draw node[above] at (0.6,1.075){\(\SI{220}{V}\)};
        \draw node[above] at (2.525,1){\(\SI{6,3}{V}\)};
        \draw node[below] at (5.5,-1.1){A};
        \draw node[below] at (6.8,-1.1){K};
    
\end{circuitikz}
```

## [NOFY024] Úloha VII

### Měření indukčnosti cívky \(L\), kapacity kondenzátoru \(C\), vnitřního odporu cívky \(R_L\) a vnitřního odporu kondenzátoru \(R_C\)

**Zkompilované PDF:** [[NOFY024]_Úloha_VII_schema_1.pdf]([NOFY024]_Úloha_VII_schema_1.pdf)

```latex
\begin{circuitikz}[]

        \draw (-1.5,-1) to [dcvsource, o-o] (-1.5,1);
        \draw (-1.5,-0.5) to [rmeterwa] (-1.5,0.5);
        \draw (0,-1) to [sV, o-o] (0,1);
        \draw (0,-0.5) to [rmeterwa] (0,0.5);
        \draw (1,-1) to [short, o-] (1,-1) -- (1,-2) -- (4,-2) to [rmeter, t=V, *-] (4,0.25);  
        \draw (4,0.5) node[cute spdt mid, rotate=90](Sw1){} ;
        \draw (3.55,0.8) -- (2.5,0.8) -- (2.5,2) -- (1,2) to [short, -o] (1,1);
        \draw (4.45,0.8) -- (5.5,0.8) -- (5.5,2) -- (6.5,2) to [short, -o] (6.5,1.75);
        \draw (6.5,-1.75) to [short, o-] (6.5,-1.75) -- (6.5,-2) -- (4,-2);
        \draw (7.5,1.75) to [european resistor=\(R_L\),o-] (7.5,0) to [L=\(L\),-o]
        (7.5,-1.75);
        \draw (9.5,1.75) to [short, o-] (9.5,1.75) -- (9.5,1.25) to [short, *-] (9.5,1.25) -- (8.75,1.25) to [european resistor=\(R_C\)] (8.75,-1.25) -- (9.5,-1.25) to [short, *-] (9.5,-1.25) -- (10.25,-1.25) to [C] (10.25,1.25) -- (9.5,1.25);
        \draw (9.5,-1.25) -- (9.5,-1.75) to [short, o-](9.5,-1.75);
        \draw (10.65,0) node[right]{\(C\)};
        \draw (2.5,2) to [rmeter, t=A, *-*] (5.5,2);
        \draw (3.55,0.8) node[above]{a};
        \draw (4.45,0.8) node[above]{b};
    
\end{circuitikz}
```

### Čtyřbodová metoda

**Zkompilované PDF:** [[NOFY024]_Úloha_VII_schema_2.pdf]([NOFY024]_Úloha_VII_schema_2.pdf)

```latex
\begin{circuitikz}[european, bigR/.style={R, bipoles/length=2cm}]

        \draw (0,0) to [short, o-] (0,0) to [rmeter, t=A] (2,0) to [bigR, o-o] (5,0) -- (6,0) to [short, o-] (6,0);
        \draw (3.5,0.25) node[above]{\(R\)};
        \draw (3,-0.3) to [short, o-] (3,-0.3) -- (3,-0.55) -- (2.5,-0.55) -- (2.5,-1) to [rmeter, t=V] (4.5,-1) -- (4.5,-0.55) -- (4,-0.55) -- (4,-0.3) to [short, -o] (4,-0.3);
        \draw (2,0) node[above]{1};
        \draw (5,0) node[above]{2};
        \draw (3,-0.3) node[above]{3};
        \draw (4,-0.3) node[above]{4};
    
\end{circuitikz}
```

## [NOFY024] Úloha IX

### Měření statické charakteristiky termistoru

**Zkompilované PDF:** [[NOFY024]_Úloha_IX_schema_1.pdf]([NOFY024]_Úloha_IX_schema_1.pdf)

```latex
\begin{circuitikz}[european]

        \draw (0,0) to [sR=T, *-*] (3,0) to [R=R, -*] (6,0) -- (6,1.5) to [rmeter, t=mA] (3,1.5);
        \draw (0,0) -- (0,2.05) to [pR=P, name=P, mirror, *- ] (3,2.05) -- (3,3.5) to [dcvsource, o-o, a=\(U\)] (0,3.5) -- (0,2.05);
        \draw (3,1.5) -- (P.wiper);
        \draw (0,0) -- (0,-1) to [rmeter, t=V] (3,-1) -- (3,0);
        \draw (0,0) node[left]{A} (3,0) node[above]{C} (6,0) node[right]{B} ;
    
\end{circuitikz}
```

### Měření teplotní závislosti odporu termistoru

**Zkompilované PDF:** [[NOFY024]_Úloha_IX_schema_2.pdf]([NOFY024]_Úloha_IX_schema_2.pdf)

```latex
\begin{circuitikz}[european,  bigR/.style={R, bipoles/length=2cm}]

        \draw (0,0) to [sR=T, *-*] (3,0) to [R=R, -*] (6,0);
        \draw (0,0) -- (0,-2) to [rmeter, t=\(\ohm\)] (3,-2) -- (3,0);
        \draw (0,0) node[left]{A} (3,0) node[above]{C} (6,0) node[right]{B};
        \draw (-1,-1) to [short, *-] (-1,-1) -- (-0.25,-1) to [crossing] (0.25,-1) to [bigR] (2.75,-1) to [crossing] (3.25,-1) to [short, -*] (4,-1) -- (4,-3) to [dcvsource, o-o] (-1,-3) -- (-1,-1);
        \draw (1.5,-1.25) node[above]{\tiny topná spirála};
        \draw (1.7, -3.5) node[right]{\(U\)};
        \draw (0,1.5) to [bigR,*-*] (3,1.5) -- (3,3) to  [rmeter, t=\(\ohm\)] (0,3) -- (0,1.5);
        \draw (1.5,1.25) node[above]{\small Pt 100};
        \draw (-1,-1) node[left]{Ž};
        \draw (4,-1) node[right]{Ž};
        \draw (0,1.5) node[left]{\(\mathrm{R_t}\)};
        \draw (3,1.5) node[right]{\(\mathrm{R_t}\)};
        \draw [line width=1.5pt, dashed] (-1.75,2.25) rectangle (6.75,-1.45);
    
\end{circuitikz}
```

## [NOFY024] Úloha X

### Měření vodivosti

**Zkompilované PDF:** [[NOFY024]_Úloha_X_schema_1.pdf]([NOFY024]_Úloha_X_schema_1.pdf)

```latex
\begin{circuitikz}[european]

        \draw (0,-1) to [dcvsource, o-o] (0,1) -- (0,2)
        to [rmeter=\(0-5 \text{ mA}\), t=mA] (5,2) -- (5,1) 
        to [R,o-o] (5,-1) -- (5,-2) -- (0,-2) -- (0,-1);
        \draw (5.25,0.45) to [short, o-]  (6.25,0.45) -- (6.25,1) -- (7.5,1) to [rmeter, t=V] (7.5,-1) -- (6.25,-1) -- (6.25,-0.45) -- (5.25,-0.45) to [short,o-] (5.25,-0.45);
        \draw (5,1) node[left]{1};
        \draw (5,-1) node[left]{2};
        \draw (5.25,0.8) node[right]{3};
        \draw (5.25,-0.8) node[right]{4};
    
\end{circuitikz}
```

### Napájení elektromagnetu

**Zkompilované PDF:** [[NOFY024]_Úloha_X_schema_2.pdf]([NOFY024]_Úloha_X_schema_2.pdf)

```latex
\begin{circuitikz}[european, cute inductors, longL/.style = {cute inductor, inductors/scale=0.75, inductors/width=3.5, inductors/coils=25}]

        \draw (0,-1) to [dcvsource, o-o] (0,1) -- (0,3)
        to [rmeter=\(0-4 \text{ A}\), t=A] (5,3) -- (5,2.5) -- (5.5,2.5) 
        node[cute spdt mid](Sw1){} 
        (Sw1.out 1) -- (7,2.92) --++(0,-0.5)
        to [longL]  (7,-1.58) -- (7,-2.08);
        \draw (0,-1.05) -- (0,-3) -- (5,-3) -- (5,-2.5) -- (5.5,-2.5)
        node[cute spdt mid](Sw2){}
        (Sw2.out 1) -- (7,-2.08);
        \draw (5.8,2.02) -- (5.8,-2.02);
        \draw (Sw2.out 2) -- (6.3,-2.92) to [crossing] (6.3,-1.25) -- (6.3,2.45) to [crossing] (6.3,3.4) -- (5.8,3.4) -- (5.8,2.98);
        \draw [line width=1.5pt, dashed] (Sw1.mid) -- (Sw2.mid);
    
\end{circuitikz}
```

## [NOFY024] Úloha XI

### Měření voltampérové charakteristiky diody (v propustné oblasti)

**Zkompilované PDF:** [[NOFY024]_Úloha_XI_schema_1.pdf]([NOFY024]_Úloha_XI_schema_1.pdf)

```latex
\begin{circuitikz}[]

            \draw (0,0.5) node[left]{\(+\)};
            \draw (0,0.5) node[ocirc]{};
            \draw (0,-0.5) node[left]{\(-\)};
            \draw (0,-0.5) node[ocirc]{};
            \draw (0,0.5) -- (0,1) to [rmeter, t=mA] (2.5,1) -- (4,1) to [Do] (4,-1) -- (0,-1) -- (0,-0.5);
            \draw (2.5,1) to [rmeter, t=V, *-*] (2.5,-1);
            \draw (4,0.75) node[right]{A};
            \draw (4,-0.75) node[right]{K};
        
\end{circuitikz}
```

### Měření voltampérové charakteristiky diody (v závěrné oblasti)

**Zkompilované PDF:** [[NOFY024]_Úloha_XI_schema_2.pdf]([NOFY024]_Úloha_XI_schema_2.pdf)

```latex
\begin{circuitikz}[]

            \draw (0,0.5) node[left]{\(-\)};
            \draw (0,0.5) node[ocirc]{};
            \draw (0,-0.5) node[left]{\(+\)};
            \draw (0,-0.5) node[ocirc]{};
            \draw (0,0.5) -- (0,1) to [rmeter, t=mA] (2.5,1) -- (4,1) to [Do] (4,-1) -- (0,-1) -- (0,-0.5);
            \draw (2.5,1) to [rmeter, t=V, *-*] (2.5,-1);
            \draw (4,0.75) node[right]{A};
            \draw (4,-0.75) node[right]{K};
        
\end{circuitikz}
```

### Zapojení Zenerovy diody do obvodu s A/D převodníkem

**Zkompilované PDF:** [[NOFY024]_Úloha_XI_schema_3.pdf]([NOFY024]_Úloha_XI_schema_3.pdf)

```latex
\begin{circuitikz}[european]

        \draw (0,-1) to [dcvsource ,o-o] (0,1) -- (1,1) to [vR, *-*] (3,1) -- (4,1) to [zDo, *-*] (6,1) -- (6.5,1) -- (6.5,-1) -- (0,-1);
        \draw (1,1) -- (1,2) -- (5,2) -- (5,3) node[circ]{};
        \draw (3,1) -- (3,1.75) -- (5.5,1.75) -- (5.5,3) node[circ]{};
        \draw (6,1) -- (6,2.25) -- (5.75,2.25) to [crossing] (5.25,2.25) to [crossing] (4.75,2.25) -- (4,2.25) -- (4,3) node[circ]{};
        \draw (4,1) -- (4,1.5) -- (4.5,1.5) -- (4.5,1.625) to [crossing] (4.5,1.875) to [crossing] (4.5,2.125) to [crossing] (4.5,2.375) -- (4.5,3) node[circ]{};
        \draw (4,3) node[above]{1};
        \draw (4,3.4) node[above]{Hi};
        \draw (4.5,3) node[above]{2};
        \draw (4.5,3.4) node[above]{Lo};
        \draw (5,3) node[above]{3};
        \draw (5,3.4) node[above]{Hi};
        \draw (5.5,3) node[above]{4};
        \draw (5.5,3.4) node[above]{Lo};
        \draw (4.75,4) node[above]{A/D modul};
        \draw (3.5,5) rectangle (6,2.5);
        \draw (1,4) node[currarrow, rotate=180](A1){};
        \draw (3,4) node[currarrow](A2){};
        \draw [line width=1.5pt, dashed] (3,4) -- (1,4);
        \draw (0.75,4) node[left]{USB};
        \draw (4.25,1) node[below]{A};
        \draw (5.75,1) node[below]{K};
        \draw (1,1.5) node[left]{Hi};
        \draw (3,1.3) node[right]{Lo};
        \draw (4.3,1) node[above]{Lo};
        \draw (6,1.5) node[right]{Hi};
    
\end{circuitikz}
```

### Obvod pro stabilizaci stejnosměrného napětí

**Zkompilované PDF:** [[NOFY024]_Úloha_XI_schema_4.pdf]([NOFY024]_Úloha_XI_schema_4.pdf)

```latex
\begin{circuitikz}[european]

        \draw (0,1) node[left]{\(+\)};
        \draw (0,-1) node[left]{\(-\)};
        \draw (0,-1) to [open, v^=\(U_1\),o-o] (0,1) to [R=\(R_S\)] (3,1) -- (4,1); \draw (4,-1) to [open, v_=\(U_0\),o-o] (4,1);
        \draw (4,-1) -- (0,-1);
        \draw (4,1) node[right]{a};
        \draw (4,-1) node[right]{b};
        \draw (3,-1) to [zDo, *-*] (3,1);
        \draw (2.75,0.5) node[left]{K};
        \draw (2.75,-0.5) node[left]{A};
    
\end{circuitikz}
```

## [NOFY024] Úloha XVIII

### Oscilační RLC obvod

**Zkompilované PDF:** [[NOFY024]_Úloha_XVIII_schema_1.pdf]([NOFY024]_Úloha_XVIII_schema_1.pdf)

```latex
\begin{circuitikz}[]

        \draw (0,-1) to [dcvsource, o-o] (0,1);
        \draw (0,-0.5) to [rmeterwa] (0,0.5);
        \draw (0,-1) node[left]{\(-\)};
        \draw (0,1) node[left]{\(+\)};
        \draw (0.05,-1) -- (1.88,-1) -- (1.88,0.2);
        \draw (1.83,1) node[above]{\(+\)};
        \draw (1.88,0.2) node[left]{\(-\)};
        \draw (1.83,1) -- (0.05,1);
        \draw (2.48,1) --++ (0,-0.4);
        \draw (2.18,0.57) node[cute spdt down arrow, rotate = 180]{};
        \draw (2.48,1) -- (3,1) to [L=\(L\)] (5,1) to [C=\(C\)] (7,1) -- (7.5,1) to [european resistor=\(R\),*-*] (7.5,-1) to [short, -*] (1.88,-1);
        \draw (7.5,1) -- (9,1) to [rmeter, t=V, l={{{{\rotatebox[origin=c]{90}{\footnotesize ISES}}}}}] (9,-1) -- (7.5,-1);
    
\end{circuitikz}
```

### Relaxační RC obvod

**Zkompilované PDF:** [[NOFY024]_Úloha_XVIII_schema_2.pdf]([NOFY024]_Úloha_XVIII_schema_2.pdf)

```latex
\begin{circuitikz}[]

        \draw (0,-1) to [dcvsource, o-o] (0,1);
        \draw (0,-0.5) to [rmeterwa] (0,0.5);
        \draw (0,-1) node[left]{\(-\)};
        \draw (0,1) node[left]{\(+\)};
        \draw (0.05,-1) -- (1.88,-1) -- (1.88,0.2);
        \draw (1.83,1) node[above]{\(+\)};
        \draw (1.88,0.2) node[left]{\(-\)};
        \draw (1.83,1) -- (0.05,1);
        \draw (2.48,1) --++ (0,-0.4);
        \draw (2.18,0.57) node[cute spdt down arrow, rotate = 180]{};
        \draw (2.48,1) -- (3,1) to [european resistor=\(R\)] (5,1) -- (5.5,1) to [C=\(C\),*-*] (5.5,-1) to [short, -*] (1.88,-1);
        \draw (5.5,1) -- (7,1) to [rmeter, t=V, l={{{{\rotatebox[origin=c]{90}{\footnotesize ISES}}}}}] (7,-1) -- (5.5,-1);
    
\end{circuitikz}
```

## [NOFY024] Úloha S-XVIII

### Oscilační RLC obvod

**Zkompilované PDF:** [[NOFY024]_Úloha_S-XVIII_schema_1.pdf]([NOFY024]_Úloha_S-XVIII_schema_1.pdf)

```latex
\begin{circuitikz}[]

        \draw (0,-1) to [dcvsource, o-o] (0,1);
        \draw (0,-0.5) to [rmeterwa] (0,0.5);
        \draw (0,-1) node[left]{\(-\)};
        \draw (0,1) node[left]{\(+\)};
        \draw (0.05,-1) -- (1.88,-1) -- (1.88,0.2);
        \draw (1.83,1) node[above]{\(+\)};
        \draw (1.88,0.2) node[left]{\(-\)};
        \draw (1.83,1) -- (0.05,1);
        \draw (2.48,1) --++ (0,-0.4);
        \draw (2.18,0.57) node[cute spdt down arrow, rotate = 180]{};
        \draw (2.48,1) -- (3,1) to [L=\(L\)] (5,1) to [C=\(C\)] (7,1) -- (7.5,1) to [european resistor=\(R\),*-*] (7.5,-1) to [short, -*] (1.88,-1);
        \draw (7.5,1) -- (9,1) to [rmeter, t=V] (9,-1) -- (7.5,-1);
    
\end{circuitikz}
```

## [NOFY024] Úloha XIX

### Napájení cívky

**Zkompilované PDF:** [[NOFY024]_Úloha_XIX_schema_1.pdf]([NOFY024]_Úloha_XIX_schema_1.pdf)

```latex
\begin{circuitikz}[european, cute inductors, longL/.style = {cute inductor, inductors/scale=0.75, inductors/width=2, inductors/coils=15}]

        \draw (0,-1) to [dcvsource, o-o] (0,1) -- (0,1.5) to [rmeter, t=A] (3,1.5) to [longL] (3,-1.5) -- (0,-1.5) -- (0,-1);
        \draw (0,-0.5) to [rmeterwa] (0,0.5);
        \draw (3.8,0) to [open] (3.5,1);
    
\end{circuitikz}
```

## [NOFY024] Úloha XXI

### Vlastní měření vlastností feritových kroužků

**Zkompilované PDF:** [[NOFY024]_Úloha_XXI_schema_1.pdf]([NOFY024]_Úloha_XXI_schema_1.pdf)

```latex
\begin{circuitikz}[]

        \draw (0,-1.1) -- (0,-0.8) to [sV, o-o, l={{{{\rotatebox[origin=c]{90}{\footnotesize AC 250 K1D}}}}}, ] (0,0.7) -- (0,1) -- ++(1,0)
        node[transformer core, circuitikz/inductors/coils=6,anchor=A1](T){};
        \draw (T.A2) -- ++ (-1,0);
        \draw (T.base) node[above]{trafo};
        \draw (T.B1) to [rmeter, t=mA] (5,1)  node[transformer, circuitikz/inductors/coils=6,anchor=A1](F){};
        \draw (F.base) node[above]{ferit};
        \draw (F.A2)  to [european resistor = \(\SI{2,2}{\ohm}\),*-*] (T.B2);
        \draw (F.B1) --++ (0,-0.6) --++ (0.5,0) node[fourport, anchor=port4, t=\huge\(\int\)](I){};
        \draw (I.port1) --++ (-0.5,0) --++ (0,-0.6);
        \ctikzset{bipoles/oscope/width=1.8}\ctikzset{bipoles/oscope/height=1.2}
        \draw (I.port3) --++ (0.5,0) --++ (0,-1) --++ (1,0) node[oscopeshape, anchor =in 1](O){};
        \draw node[bnc, anchor=zero, rotate=-180](bcn1) at (O.in 1){};
        \draw node[right] at (O.in 1){\(\,y\)};
        \draw node[bnc, anchor=zero](bcn2) at (O.in 2){};
        \draw node[left] at (O.in 2){\(x\,\)};
        \draw (bcn1.shield) ++ (0,-0.3) --++ (0,-0.2) --++ (-1.25,0) --++ (0,0.45) -- (I.port2);
        \draw (bcn2.shield) --++ (0,-1) --++ (-6.925,0) --++ (0,0.7);
        \draw (bcn2.hot) --++ (0.25,0) --++ (0,-1.5) --++ (-9.225,0) --++ (0,1);
    
\end{circuitikz}
```

### Kalibrace vertikální osy osciloskopu

**Zkompilované PDF:** [[NOFY024]_Úloha_XXI_schema_2.pdf]([NOFY024]_Úloha_XXI_schema_2.pdf)

```latex
\begin{circuitikz}[]

        \draw (0,-1.1) -- (0,-0.8) to [sV, o-o, l={{{{\rotatebox[origin=c]{90}{\footnotesize AC 250 K1D}}}}}, ] (0,0.7) -- (0,1) -- ++(1,0)
        node[transformer core, circuitikz/inductors/coils=6,anchor=A1](T){};
        \draw (T.A2) -- ++ (-1,0);
        \draw (T.base) node[above]{trafo};
        \draw (T.B1) -- (3,1) -- (4,1) to [european resistor] (6.5,1) to [european resistor = \(\SI{1}{\ohm}\),*-*] (6.5,-1.1);
        \draw node[above] at (5.25,1.6){odporová};
        \draw node[above] at (5.25,1.2){dekáda};
        \draw (6,-1.1) -- (T.B2);
        \draw (6,1) --++ (1.5,0) --++ (0,-0.6) --++ (0.5,0) node[fourport, anchor=port4, t=\huge\(\int\)](I){};
        \draw (I.port1) --++ (-0.5,0) --++ (0,-0.6) --++ (-1.5,0);
        \ctikzset{bipoles/oscope/width=1.8}\ctikzset{bipoles/oscope/height=1.2}
        \draw (I.port3) --++ (0.5,0) --++ (0,-1) --++ (1,0) node[oscopeshape, anchor =in 1](O){};
        \draw node[bnc, anchor=zero, rotate=-180](bcn1) at (O.in 1){};
        \draw node[right] at (O.in 1){\(\,y\)};
        \draw node[bnc, anchor=zero](bcn2) at (O.in 2){};
        \draw node[left] at (O.in 2){\(x\,\)};
        \draw (bcn1.shield) ++ (0,-0.3) --++ (0,-0.2) --++ (-1.25,0) --++ (0,0.45) -- (I.port2);
        \draw (3.5,1) to [rmeter, t=V, *-*] (3.5,-1.1);
        \draw node[left, rotate=90] at (6,0.75){normál};
    
\end{circuitikz}
```

