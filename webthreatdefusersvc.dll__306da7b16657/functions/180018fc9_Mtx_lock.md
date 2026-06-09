# _Mtx_lock

- ea: `0x180018fc9`
- end: `0x180018fcf`
- name: `_Mtx_lock`
- size: `6`
- prototype: `int __cdecl(_Mtx_t)`
- caller_count: `20`
- callee_count: `0`
- tags: ``

## callers

- `0x180007724`
- `0x180007e2c`
- `0x18000903c`
- `0x18000b500`
- `0x18000bce0`
- `0x18000c3b0`
- `0x18000c59c`
- `0x18000cc70`
- `0x18000cd80`
- `0x18000d120`
- `0x18000d7f8`
- `0x18000e118`
- `0x18000e360`
- `0x18000e73c`
- `0x18000ea20`
- `0x18000f0e4`
- `0x18000f168`
- `0x18000f264`
- `0x18000f408`
- `0x18000f540`

## import_xrefs

- `msvcp_win!_Mtx_lock` at `0x180018fc9`

## pseudocode

```c
// attributes: thunk
int __cdecl Mtx_lock(_Mtx_t a1)
{
  return _Mtx_lock(a1);
}

```

## disassembly

```asm
0x180018fc9  jmp     cs:__imp__Mtx_lock
```
