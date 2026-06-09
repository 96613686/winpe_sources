# EPATHOBJ_bMoveTo_0

- ea: `0x14001791c`
- end: `0x140017923`
- name: `EPATHOBJ_bMoveTo_0`
- size: `7`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140003860`

## import_xrefs

- `win32kbase!EPATHOBJ_bMoveTo` at `0x14001791c`

## pseudocode

```c
// attributes: thunk
__int64 EPATHOBJ_bMoveTo_0()
{
  return EPATHOBJ_bMoveTo();
}

```

## disassembly

```asm
0x14001791c  jmp     cs:__imp_EPATHOBJ_bMoveTo
```
