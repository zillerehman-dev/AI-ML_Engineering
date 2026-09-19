# Matplotlib — The Complete Reference Notebook

This will give you the core ideas of Matplotlib:
what it is, the handful of concepts everything else is built on, the
main graph types and when to use each one, and the attributes you'll
reach for constantly. If you only have time to read one thing before
using the library, read this.

---

## What Matplotlib actually is

Matplotlib turns numbers into pictures. You give it lists of numbers,
and it draws lines, bars, dots, or colored grids from them. Everything
else in the library is just variations on that one idea.

---

## The two concepts everything is built on

- **Figure** — the whole blank page or canvas. One Figure can hold one
  chart, or many charts arranged in a grid.
- **Axes** — one individual chart area sitting inside the Figure (not
  to be confused with "axis", the x or y line). A Figure with 4 charts
  side by side has 1 Figure and 4 Axes.

The standard way to create both at once:

```python
fig, ax = plt.subplots()          # one chart
fig, axes = plt.subplots(2, 3)    # a 2x3 grid of 6 charts, axes[row, col]
```

Every chart follows the same basic recipe:

```python
fig, ax = plt.subplots()      # 1. make the canvas + chart area
ax.plot(x, y)                 # 2. draw something on it
ax.set_title("...")           # 3. add title/labels/legend
ax.set_xlabel("...")
ax.legend()
plt.savefig("chart.png")      # 4. save it (optional)
plt.show()                    # 5. display it
```

Once that five-step pattern is automatic, every new chart type is just
swapping step 2 for a different method.

---

## The main graph types, and when to reach for each

| Graph | Use it when... | Function |
|---|---|---|
| **Line plot** | Data has a natural order, usually time (sales over months, loss over epochs) | `ax.plot(x, y)` |
| **Scatter plot** | Checking if two variables are related, or spotting clusters/groups | `ax.scatter(x, y)` |
| **Histogram** | Understanding the shape/spread of one variable — is it balanced, skewed, are there outliers? | `ax.hist(data, bins=n)` |
| **Box plot** | Comparing spread across several groups at once, and spotting outliers precisely | `ax.boxplot(data)` |
| **Bar chart** | Comparing sizes across separate categories (not a continuous trend) | `ax.bar(categories, values)` |
| **Heatmap** (e.g. confusion matrix) | Showing a 2D grid of numbers as color, so patterns jump out visually | `ax.imshow(array, cmap=...)` |
| **Filled contour plot** | Shading in regions of a 2D space based on a condition — e.g. a classifier's decision boundary | `ax.contourf(x_grid, y_grid, values)` |

A rule of thumb: line = order matters, scatter = relationship between
two things, histogram/box plot = shape of one thing, bar = comparing
categories, heatmap/contour = a full 2D surface of values.

---

## Machine learning-specific plots worth knowing

- **Loss/accuracy curves** are just line plots — training loss and
  validation loss plotted together over epochs. If validation loss
  starts climbing back up while training loss keeps falling, that's
  overfitting (the model is memorizing rather than learning).
- **Confusion matrix** is a heatmap (`imshow`) of a small grid: rows =
  the true category, columns = what the model predicted. It shows
  exactly which categories get confused with each other — something a
  single accuracy number can't tell you.
- **Decision boundary** is a filled contour plot (`contourf`): you run
  a classifier across a fine grid of points covering the whole chart,
  then shade each region by what the classifier predicted there, and
  plot the real data points on top.
- **ROC curve / Precision-Recall curve** show how a classifier performs
  across every possible decision threshold, not just the one you picked.
  A curve that hugs the top-left (ROC) or top-right (Precision-Recall)
  corner is a strong model; a curve near the diagonal is close to random
  guessing.

---

## Attributes and arguments you'll use constantly

| Argument | What it controls |
|---|---|
| `figsize=(w, h)` | Size of the whole Figure, in inches |
| `color="..."` | Color of a line, dots, or bars |
| `alpha=0-1` | Transparency (0 = invisible, 1 = solid) — useful for overlapping points |
| `label="..."` | Name shown for that item once you call `.legend()` |
| `marker="o"` / `"s"` | Shape drawn at each data point on a line/scatter |
| `linestyle="--"` | `-` solid, `--` dashed, `:` dotted |
| `bins=n` | Number of buckets a histogram splits data into |
| `cmap="..."` | Color scale used for a heatmap or filled contour |
| `edgecolor="..."` | Outline color around bars/dots/shapes |
| `dpi=300` | Sharpness when saving an image — 300 is standard for print |
| `bbox_inches="tight"` | Trims blank space when saving, so nothing gets cut off |

Common finishing touches on almost every chart:
`ax.set_title()`, `ax.set_xlabel()` / `ax.set_ylabel()`, `ax.legend()`,
`ax.grid(True)`, and `plt.tight_layout()` (fixes overlapping titles/labels
when you have multiple charts in one Figure).

---

## Two NumPy helpers you'll always see alongside Matplotlib

- **`np.linspace(start, stop, count)`** — gives you an exact NUMBER of
  evenly spaced values between two points (both ends included). Used to
  generate smooth x-values for drawing curves.
  `np.linspace(0, 10, 5)` gives `[0, 2.5, 5, 7.5, 10]`. Compare to
  `np.arange(start, stop, step)`, which instead lets you set the exact
  GAP size between values, and does not include the `stop` value.
- **`np.meshgrid(x_values, y_values)`** — builds every (x, y) coordinate
  combination across a 2D area, like marking every intersection point on
  graph paper. This is how a decision boundary plot tests a classifier
  at every point across the whole chart, not just at the original data
  points.

---

## Bonus: graph types not in the notebook, worth knowing exist

- **Pie chart** (`ax.pie`) — parts of a whole, best with few categories.
- **Stacked bar / area plot** (`ax.bar(..., bottom=...)`, `ax.stackplot`) —
  showing a total and its breakdown together over time.
- **Error bar plot** (`ax.errorbar`) — shows a margin of uncertainty
  around each point.
- **Violin plot** (`ax.violinplot`) — like a box plot, but shows the full
  shape of the distribution, not just five summary numbers.
- **Twin axes** (`ax.twinx()`) — plot two lines with very different
  scales on the same chart, sharing the x-axis.
