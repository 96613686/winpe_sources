# EPATHOBJ_bPolyLineTo_0

- ea: `0x14001792e`
- end: `0x140017935`
- name: `EPATHOBJ_bPolyLineTo_0`
- size: `7`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140003860`

## import_xrefs

- `win32kbase!EPATHOBJ_bPolyLineTo` at `0x14001792e`

## pseudocode

```c
// attributes: thunk
__int64 EPATHOBJ_bPolyLineTo_0()
{
  return EPATHOBJ_bPolyLineTo();
}

```

## disassembly

```asm
0x14001792e  jmp     cs:__imp_EPATHOBJ_bPolyLineTo
```
