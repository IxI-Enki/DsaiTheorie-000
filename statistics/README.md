# Statistik

  Anbei ein Datensatz welcher die Monatsgehälter (in EUR) von 20 Mitarbeitern eines Unternehmens enthält.  
  Es sollen damit die Berechnung grundlegender statistischer Maße wie Mittelwert, Median, Modus, Spannweite, Varianz und Standardabweichung gezeigt werden.  

## Gehaltsdaten

<div align="center">

| Mitarbeiter | Gehalt [€] | | Mitarbeiter | Gehalt [€] |  
| :---------: | :--------: |-| :---------: | :--------: |  
| MA_1        | 2000       | | MA_11       | 3500       |  
| MA_2        | 2100       | | MA_12       | 3600       |  
| MA_3        | 2200       | | MA_13       | 3800       |  
| MA_4        | 2300       | | MA_14       | 4000       |
| MA_5        | 2400       | | MA_15       | 4200       |
| MA_6        | 2500       | | MA_16       | 4500       |  
| MA_7        | 2600       | | MA_17       | 5000       | 
| MA_8        | 2700       | | MA_18       | 5500       | 
| MA_9        | 2800       | | MA_19       | 6000       |
| MA_10       | 3000       | | MA_20       | 12000      | 

</div>

--- 

## Interpretation der statistischen Maße

## Mittelwert (Durchschnitt)
  Er zeigt den durchschnittlichen Verdienst in diesem Unternehmen.  
  Der Mittelwert wird stark von Ausreißern beeinflusst.

<div align="center">

  $$ Mittelwert = \frac{\sum x_i}n $$

  $$ \sum x_i = Summe\ aller\ Gehälter $$
  
  $$ n = Anzahl\ der\ Personen\ im\ Datensatz $$

---

- <p align="left"> 1. Summe aller Gehälter: </p>
  
  \[ 2000+2200+2200+...+12000 = 77000\ EUR \]

- <p align="left"> 2. Anzahl der Personen: </p>

  \[ n = 20 \]

- <p align="left"> 3. Mittelwert berechnen: </p>

  \[ Mittelwert = \frac{77000}2 = 3850\ EUR \] 
  

<div align="left">

--- 

## Median

  Er **teilt den Datensatz in zwei Hälften**:  
  > Die eine Hälfte der Mitarbeiter verdient weniger, die andere mehr.  
  
  *Der Median ist robuster gegenüber Ausreißern als der Mittelwert.*

  1. Datensatz **sortieren**  
  2. **Anzahl** der Werte feststellen  
  3. **Mittleren Werte** sind an Stelle 10 und 11  

</div>

  $$ Median = \frac{3000+3500}2 = 3250\ EUR $$ 


<div align="left">

---

## Modus

Der Modus **zeigt den häufigsten Wert**.

*Eine Clusterung in Bereiche kann Sinn machen.*

*Der Modus ist nützlich für kategorische Daten*
  > z.B. häufige Antworten bei Umfragen.

  1. Zählen der Häufigkeit jedes Wertes.
  2. Der am häufigsten vorkommende Wert ist der Modus.
  3. Der Wert 2500 EUR kommt 2 mal vor.

---
## Spannweite

Sie gibt an, wie groß der **Unterschied** zwischen dem **höchsten und niedrigsten Wert** ist.  

*Die Spannweite ist ein sehr einfaches **Maß für die Streuung**.*  

</div>

$$ Spannweite = max_{(x_i)} - min_{(x_i)} $$

$$ max_{(x_i)} = der\ größte\ Wert\ im\ Datensatz $$
$$ min_{(x_i)} = der\ kleinste\ Wert\ im\ Datensatz $$ 

$$ Maximalwert\ (höchstes\ Gehalt)  = 12\ 000\ EUR $$
$$ Minimalwert\ (niedrigstes\ Gehalt) = 2\ 000\ EUR $$

$$ Spannweite = 12\ 000 - 2\ 000 = 10\ 000\ EUR $$


<div align="left">

---

## Varianz

Sie misst die **durchschnittliche quadratische Abweichung** vom Mittelwert.

</div>

$$ Varianz = \frac{1}n \sum_{i=1}^{n}{(x_i-\bar{x})^2} $$

<div align="left">

  1. Mittelwert berechnen
  2. Abweichung jedes Wertes zum Mittelwert berechnen
  3. Abweichungen quadrieren *(damit werden sie positiv)*
  4. Summe bilden
  5. durch die Anzahl der Werte dividieren

---

## Standardabweichung

Die Standardabweichung misst die **durchschnittliche Abweichung der Werte vom Mittelwert** in einem Datensatz.  

*Sie zeigt an, wie stark die einzelnen Werte um den Mittelwert **streuen**.*  

> - Je größer die Standardabweichung, desto weiter liegen die Werte auseinander.  
> - Eine kleine Standardabweichung bedeutet, dass die Werte eng um den Mittelwert gruppiert sind.  

</div>

$$ Standardabweichung = \sqrt{\frac{1}n \sum_{i=1}^{n}{(x_i-\bar{x})^2}} $$

---

## Statistische Maße

| Maß                | Wert        |
| :----------------- | :---------: |
| Mittelwert         | 3840    EUR |
| Median             | 3250    EUR |
| Modus              | 2500    EUR |
| Spannweite         | 10000   EUR |
| Varianz            | 5042526 EUR |
| Standardabweichung | 2245    EUR |


## Diagramm

<img src="../img/chart.svg" alt="chart">
 


<!----{
  "$schema": "https://vega.github.io/schema/vega/v5.json",
  "description": "A basic bar chart example with value labels, vertical lines, and legend.",
  "width": 650,
  "height": 400,
  "padding": 15,
  "title": {
    "text": "Verteilung der Gehälter",
    "color": "#fff",
    "fontSize": 20,
    "font": "DejaVu Sans Mono"
  },
  "config": {
    "background": "null",
    "axis": {
      "labelColor": "#fff"
    }
  },
  "data": [
    {
      "name": "table",
      "values": [
        {"category": "2000", "amount": 9},
        {"category": "3000", "amount": 4},
        {"category": "4000", "amount": 3},
        {"category": "5000", "amount": 2},
        {"category": "6000", "amount": 1},
        {"category": "7000", "amount": 0},
        {"category": "8000", "amount": 0},
        {"category": "9000", "amount": 0},
        {"category": "10000", "amount": 0},
        {"category": "11000", "amount": 1},
        {"category": "12000", "amount": 0}
      ]
    },
    {
      "name": "measures",
      "values": [
        {"measure": "Modus", "value": 2500},
        {"measure": "Median", "value": 3250},
        {"measure": "Mittelwert", "value": 3840},
        {"measure": "Spannweite", "value": 10000}
 
      ]
    }
  ],

  "scales": [
    {
      "name": "xscale",
      "type": "band",
      "domain": {"data": "table", "field": "category"},
      "range": "width",
      "padding": 0,
      "paddingInner": 0.03,
      "paddingOuter": 0.05,
      "round": true
    },
    {
      "name": "yscale",
      "domain": {"data": "table", "field": "amount"},
      "nice": true,
      "range": "height"
    },
    {
      "name": "color",
      "type": "ordinal",
      "domain": {"data": "measures", "field": "measure"},
      "range": ["#ff7f0e", "#2ca02c", "#9467bd", "#1f77b4", "#d62728", "#8c564b"]
    }
  ],

  "axes": [
    {
      "orient": "bottom",
      "scale": "xscale",
      "labelFontSize": 15,
      "labelOverlap": "parity",
      "labelPadding": 5,
      "labelBaseline": "top",
      "labelBound": true,
      "title": "Gehälter in €",
      "titleColor": "#fff",
      "titleFontSize": 17,
      "titleFont": "DejaVu Sans Mono",
      "titlePadding": 17,
      "titleY": 40
    },
    {
      "orient": "left",
      "scale": "yscale",
      "labelOffset": 9,
      "labelFontSize": 15,
      "labelOverlap": "parity",
      "labelPadding": 5,
      "labelBaseline": "bottom",
      "labelBound": false,
      "title": "Häufigkeit",
      "titleColor": "#fff",
      "titleFontSize": 17,
      "titleFont": "DejaVu Sans Mono",
      "titlePadding": 17,
      "titleY": 0,
      "titleAnchor": "end",
      "titleX": -30 
    }
  ],

  "marks": [
    {
      "type": "rect",
      "from": {"data": "table"},
      "encode": {
        "enter": {
          "x": {"scale": "xscale", "field": "category", "offset": 30},
          "width": {"scale": "xscale", "band": 1},
          "y": {"scale": "yscale", "field": "amount"},
          "y2": {"scale": "yscale", "value": 0},
          "fill": {"value": "#12171f"}
        }
      }
    },
    {
      "type": "text",
      "from": {"data": "table"},
      "encode": {
        "enter": {
          "align": {"value": "center"},
          "baseline": {"value": "bottom"},
          "fill": {"value": "#fff"},
          "x": {"scale": "xscale", "field": "category", "band": 1.025},
          "y": {"scale": "yscale", "field": "amount", "offset": 20},
          "text": {"field": "amount"}
        }
      }
    },
    {
      "type": "rule",
      "from": {"data": "measures"},
      "encode": {
        "enter": {
          "x": {"value": 65   },
          "y": {"value": 0},
          "y2": {"signal": "height"},
          "stroke":{"value": "#ff7f0e"},
          "strokeWidth": {"value": 2},
          "strokeDash": {"value": [5, 5]},
          "opacity":{"value": 0.1 }

        }
      }
    },
    {
      "type": "rule",
      "from": {"data": "measures"},
      "encode": {
        "enter": {
          "x": {"value": 110   },
          "y": {"value": 0},
          "y2": {"signal": "height"},
          "stroke": {"value":"#2ca02c"},
          "strokeWidth": {"value": 2},
          "strokeDash": {"value": [5, 5]},
          "opacity":{"value": 0.15 }

        }
      }
    },
    {
      "type": "rule",
      "from": {"data": "measures"},
      "encode": {
        "enter": {
          "x": {"value": 38   },
          "x2": {"value": 614},
          "y": {"value": 180},
          "stroke": {"value":"#1f77b4"},
          "strokeWidth": {"value": 12},
          "strokeDash": {"value": [5, 0]},
          "opacity":{"value": 0.2 }
        }
      }
    },
    {
      "type": "rule",
      "from": {"data": "measures"},
      "encode": {
        "enter": {
          "x": {"value": 142   },
          "y": {"value": 0},
          "y2": {"signal": "height"},
          "stroke": {"value":"#9467bd"},
          "strokeWidth": {"value": 2},
          "strokeDash": {"value": [5, 5]},
          "opacity":{"value": 0.2 }
        }
      }
    } ,   
    
    {
      "type": "rule",
      "from": {"data": "measures"},
      "encode": {
        "enter": {
          "x": {"value": 38   },
          "x2": {"value": 614},
          "y": {"value": 180},
          "stroke": {"value":"#ffffff22"},
          "strokeWidth": {"value": 2},
          "strokeDash": {"value": [5, 0]},
          "opacity":{"value": 0.2 }
        }
      }
    },
    {
      "type": "rule",
      "from": {"data": "measures"},
      "encode": {
        "enter": {
          "x": {"value": 38   },
          "y": {"value": 140},
          "y2": {"value": 220},

          "stroke": {"value":"#ffffff22"},
          "strokeWidth": {"value": 2},
          "strokeDash": {"value": [5, 0]},
          "opacity":{"value": 0.2 }
        }
      }
    },
{
      "type": "rule",
      "from": {"data": "measures"},
      "encode": {
        "enter": {
          "x": {"value": 614   },
          "y": {"value": 140},
          "y2": {"value": 220},

          "stroke": {"value":"#ffffff22"},
          "strokeWidth": {"value": 2},
          "strokeDash": {"value": [5, 0]},
          "opacity":{"value": 0.2 }
        }
      }
    }  ,  {
      "type": "rect",
      "from": {"data": "table"},
      "encode": {
        "enter": {
          "x": {"value": 78},
          "width": { "value": 265},
          "y": {"value": 140 },
          "y2": {"value": 220 },
          "fill": {"value": "#ffffff22"},
          "opacity":{"value": 0.05 }

        }
      }
    }

  ],

  "legends": [
    {
      "fill": "color",
      "title": "Maß",
      "titleColor": "#fff",
      "labelColor": "#fff",
      "symbolSize": 100,
      "symbolType": "square",
      "orient": "right",
      "encode": {
        "symbols": {
          "update": {
            "stroke": {"value": "transparent"}
          }
        }
      }
    }
  ]
}
--> 
