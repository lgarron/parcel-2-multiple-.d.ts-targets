# Parcel 2 — Second Types Target

This repo shows an example with two `d.ts` targets, demonstrating that Parcel 2 runs into an error when you try to build the second one.

Repro steps:

    > npm install
    > npx parcel build --target extended-types src/extended.ts

    🚨 Build failed.
    @parcel/namer-default: Target "extended-types" declares an output file path of "dist/extended/index.d.ts" which does not match the compiled bundle type "js".
    /Users/lgarron/Code/parcel-second-types-target-simplified/package.json:4:21
      3 |   "types": "dist/main/index.d.ts",
    > 4 |   "extended-types": "dist/extended/index.d.ts",
    >   |                     ^^^^^^^^^^^^^^^^^^^^^^^^^^ Did you mean "dist/extended/index.d.js"?
      5 |   "targets": {
      6 |     "types": {},
    Try changing the file extension of "extended-types" in package.json.

Note that this repo is simplified to show the minimal amount of code/configuration to trigger this error. In practice, each `.d.ts` target would accompany a `.js` target.
