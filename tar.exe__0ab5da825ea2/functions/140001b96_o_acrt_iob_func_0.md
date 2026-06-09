# _o___acrt_iob_func_0

- ea: `0x140001b96`
- end: `0x140001b9c`
- name: `_o___acrt_iob_func_0`
- size: `6`
- prototype: `FILE *__cdecl(unsigned int Ix)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x140001d64`
- `0x140001ee4`
- `0x140003768`
- `0x14000422c`
- `0x140005680`
- `0x14000583c`
- `0x140005bbc`
- `0x1400061dc`
- `0x1400069a8`
- `0x140006db0`
- `0x140006ea4`
- `0x1400071f0`
- `0x140007314`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___acrt_iob_func` at `0x140001b96`

## pseudocode

```c
// attributes: thunk
FILE *__cdecl o___acrt_iob_func_0(unsigned int Ix)
{
  return __acrt_iob_func(Ix);
}

```

## disassembly

```asm
0x140001b96  jmp     cs:__imp___acrt_iob_func
```
