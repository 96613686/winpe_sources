# __p__commode

- ea: `0x14001a8cb`
- end: `0x14001a8d1`
- name: `__p__commode`
- size: `6`
- prototype: `int *__cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14001ada0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___p__commode` at `0x14001a8cb`

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
0x14001a8cb  jmp     cs:__imp___p__commode
```
