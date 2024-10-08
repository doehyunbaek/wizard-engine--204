# Repo reproducing https://github.com/titzer/wizard-engine/issues/204

## Prerequisites
- X86-64 Linux machine
- get v8 with [jsvu](https://github.com/GoogleChromeLabs/jsvu)

## How to preproduce

```
~/wizard-engine-#204 wasmtime --invoke main commanderkeen-187.wasm
~/wizard-engine-#204 wizeng.x86-64-linux commanderkeen-187.wasm
commanderkeen-187.wasm:0xDC03: expected 3 data segments, missing data section
~/wizard-engine-#204 ~/.jsvu/engines/v8/v8 run.js -- commanderkeen-187.wasm
run.js:94: CompileError: WebAssembly.Module(): size 8722039 > maximum function size 7654321 @+56330
  var module = new WebAssembly.Module(buffer);
               ^
CompileError: WebAssembly.Module(): size 8722039 > maximum function size 7654321 @+56330
    at run.js:94:16
```
