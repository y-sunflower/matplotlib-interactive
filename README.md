# matplotlib-interactive

Here are some notes how to create a lib that would make matplotlib interactive (for a browser), with both great default options and large possibility of customization.

## what already exists

- matplotlib already has tools to make interactive figures, but they are not designed for the web nor easy to use: https://matplotlib.org/stable/users/explain/figure/interactive.html
- mpld3: pretty good on paper but unmainted and lacks a few things that I think would be hugely beneficial for this kind of project: https://github.com/mpld3/mpld3
- there was that `mpl_to_plotly()` func from plotly but it does not work well and has been deprecated since years now
- same thing with `to_bokeh()`
