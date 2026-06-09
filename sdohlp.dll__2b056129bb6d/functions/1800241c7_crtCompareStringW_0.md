# __crtCompareStringW_0

- ea: `0x1800241c7`
- end: `0x1800241cd`
- name: `__crtCompareStringW_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180006104`

## import_xrefs

- `msvcrt!__crtCompareStringW` at `0x1800241c7`

## pseudocode

```c
// attributes: thunk
__int64 _crtCompareStringW_0()
{
  return __crtCompareStringW();
}

```

## disassembly

```asm
0x1800241c7  jmp     cs:__imp___crtCompareStringW
```
