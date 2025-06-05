# matplotlib-interactive

Here are some notes on how to create a library that would make matplotlib interactive (for a browser), with both great default options and large possibility of customization.

<br>

## What already exists

- matplotlib already has tools to make interactive figures, but they are not designed for the web nor easy to use: https://matplotlib.org/stable/users/explain/figure/interactive.html
- mpld3: pretty good on paper but unmaintained and lacks a few things that I think would be hugely beneficial for this kind of project: https://github.com/mpld3/mpld3
- there was that `mpl_to_plotly()` function from plotly but it does not work well and has been deprecated for years now
- same thing with `to_bokeh()`

<br>

## What should it do

- takes a matplotlib figure (or none with `plt.gcf()`), writes it as svg/json/whatever, and then parses it to reproduce with some JS

```py
fig, ax = plt.subplots()
# plot some stuff

interactive_matplotlib(fig)
```

where `interactive_matplotlib()` is something like:

```py
def interactive_matplotlib(fig):
   to_json_file(fig, file="figure.json")
   interac_chart = interactive_chart_from_json(file="figure.json")
   interac_chart.to_html(file="figure.html")
```

- option to add:
  - custom css
  - custom js
  - build plugins
