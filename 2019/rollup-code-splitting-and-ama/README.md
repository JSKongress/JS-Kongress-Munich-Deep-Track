# Rollup code-splitting and AMA

There is a nice blog post explaining code splitting in RollupJS:
https://levelup.gitconnected.com/code-splitting-for-libraries-bundling-for-npm-with-rollup-1-0-2522c7437697

- Tree shaking is shown in the Rollup REPL, especially problems that occur when using multiple entry points
- Rollup is hashing the code without its imports and exports.
- web worker shares code with main, shared code should be in a new module

## Performance issues

Rollup received some criticism for its performance.

- Caching in Webpack works because scope hoisting is not used.
- Transformations are cached. Webpack assumes pure loaders.
- Hashing of full text is done in Webpack so it does not re-run code generation when nothing changed.
- There is a chunk to chunk-hash map in Webpack that makes it able to just re-build the files / chunks that really
  changed.

## Impression of parcel from the view of Rollup and Webpack

Zero config does not work. Presets might be the best compromise between having approachable configurations and the full
flexibility of today where everybody needs to understand how webpack works before getting into it.
