
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