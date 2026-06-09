# __imp_load_OpenDriver

- ea: `0x18000baad`
- end: `0x18000bab9`
- name: `__imp_load_OpenDriver`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000b9b0`

## import_xrefs

- `WINMMBASE!OpenDriver` at `0x18000baad`

## pseudocode

```c
__int64 load_OpenDriver()
{
  return _tailMerge_winmmbase_dll();
}

```

## disassembly

```asm
0x18000baad  lea     rax, __imp_OpenDriver
0x18000bab4  jmp     __tailMerge_winmmbase_dll
```
