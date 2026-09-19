# NumPy A to Z — The Complete Reference Notebook (Explained Simply)

A single, self-contained Jupyter notebook that explains NumPy from the
absolute basics to advanced topics, in plain, everyday language. Every
function and attribute is explained in simple words before it is used —
no jargon left unexplained.

No external data files are required — every example uses simple, easy
data (numbers, marks, temperatures, prices) so anyone can follow along.

## Contents

1. Core Concepts and Array Basics — what `ndarray` is and how it differs from a Python list, `.shape`/`.ndim`/`.size`/`.dtype`, `np.array()`/`np.zeros()`/`np.ones()`/`np.arange()`/`np.linspace()`, dtypes and `.astype()`
2. Accessing and Manipulating Data — indexing, slicing, fancy indexing, boolean masking, `np.where()`
3. Structural and Shape Transformations — `.reshape()`, `.flatten()`/`.ravel()`, `.T`/`np.transpose()`, `np.concatenate()`/`np.vstack()`/`np.hstack()`, `np.split()`
4. Mathematical Operations and Vectorization — vectorized arithmetic, broadcasting explained with a simple example, aggregate functions and the `axis` parameter, `np.sort()`/`np.argmax()`/`np.argmin()`
5. Advanced and Specialized Modules — `np.linalg` (dot product, determinant, inverse, eigenvalues), `np.random` (including seeding for reproducibility), handling `np.nan` and `np.inf`
6. Performance Optimization — a timed loop-vs-vectorization comparison, and views vs. copies explained with a hands-on example
7. Quick Reference Cheat-Sheet

## Running it

```bash
git clone <this-repo-url>
cd <this-repo-folder>
pip install numpy jupyter
jupyter notebook NumPy_A_to_Z.ipynb
```

## Why this notebook exists

Most NumPy tutorials assume you already know what "vectorization" or
"broadcasting" means. This notebook explains those ideas the way you
would explain them to a friend who has never heard the terms before,
using everyday examples like exam marks and temperatures, then backs
every explanation with runnable code.

## License

Feel free to use, fork, and adapt this for your own learning or teaching.
