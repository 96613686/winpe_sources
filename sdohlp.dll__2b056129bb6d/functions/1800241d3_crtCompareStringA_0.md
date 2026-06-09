# __crtCompareStringA_0

- ea: `0x1800241d3`
- end: `0x1800241d9`
- name: `__crtCompareStringA_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800060f8`

## import_xrefs

- `msvcrt!__crtCompareStringA` at `0x1800241d3`

## pseudocode

```c
// attributes: thunk
__int64 _crtCompareStringA_0()
{
  return __crtCompareStringA();
}

```

## disassembly

```asm
0x1800241d3  jmp     cs:__imp___crtCompareStringA
```
