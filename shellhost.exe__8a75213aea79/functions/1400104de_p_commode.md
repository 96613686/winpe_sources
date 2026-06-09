# __p__commode

- ea: `0x1400104de`
- end: `0x1400104e4`
- name: `__p__commode`
- size: `6`
- prototype: `int *__cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14000f540`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___p__commode` at `0x1400104de`

## pseudocode

```c
// attributes: thunk
int *__cdecl _p__commode()
{
  return __p__commode();
}

```

## disassembly

```asm
0x1400104de  jmp     cs:__imp___p__commode
```
