![Zarr.js Logo](docs/logo.png)
![Top Language Badge](https://img.shields.io/github/languages/top/gzuidhof/zarr.js) ![NPM badge](https://img.shields.io/npm/v/zarr) ![License badge](https://img.shields.io/github/license/gzuidhof/zarr.js)  [![Documentation](https://img.shields.io/badge/Read%20the-documentation-1abc9c.svg)](http://guido.io/zarr.js)

---
Typescript implementation of [**Zarr**](https://zarr.readthedocs.io/en/stable/). 
> Zarr is a library for chunked, compressed, N-dimensional arrays.

## Quick start

```
npm i zarr
```
Please see the [Documentation](guido.io/zarr.js).



## Why a Typescript implementation for Zarr?
For better or for worse the browser environment is slowly becoming the world's operating system. Numerical computing with a lot of data is a poor fit for browsers, but for data visualization, exploration and result-sharing the browser is unparalleled.

With this library a workflow as such becomes possible:
* You run an experiment/workflow in Python or Julia. 
* You write results to a Zarr store, perhaps one that lives in some cloud storage.
* In a browser you create a visualization suite which allows for some interactivity. 
* You share a link to a colleague or friend.

## Thoughts
* Currently no compression settings are supported. Some compression schemes (e.g. LZMA) will be easy to port, whereas others like the Blosc family will likely require compilation to WASM.
* No great substitute for NumPy exists in the browser, I don't expect that serious data manipulation workflows will move to the browser any time soon.
* This library represents multidimensional arrays as nested arrays of TypedArrays, similar as Pyodide. Operataions such as slicing and setting all had to be implemented from scratch to mimic NumPy as closely as possible
